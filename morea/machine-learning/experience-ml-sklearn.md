---
title: "2. Decision Trees with Scikit-Learn"
published: true
morea_id: experience-ml-sklearn
morea_type: experience
morea_summary: "A basic Scikit-learn tutorial"
morea_sort_order: 6
morea_labels:
  - 3:00pm
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How can we model high-dimensional data with deep learning?

**Objectives**
* Understand how to train a neural network in Pytorch
</div>

<div class="alert alert-info" role="warning" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Jupyter Lab Binder**
<hr/>
**Note:** Click [here](https://mybinder.org/v2/gh/scikit-learn/scikit-learn/1.2.X?urlpath=lab/tree/notebooks/auto_examples/gaussian_process/plot_gpr_co2.ipynb) to download the full example code or to run this example in your browser via Binder
</div>

# Gaussian process regression (GPR) on Mauna Loa CO2 data

This example is based on [Section 5.4.3 of SciKitLearn's “Gaussian Processes for Machine Learning”](https://scikit-learn.org/stable/modules/gaussian_process.html#rw2006). It illustrates an example of complex kernel engineering and hyperparameter optimization using gradient ascent on the log-marginal-likelihood. The data consists of the monthly average atmospheric CO2 concentrations (in parts per million by volume (ppm)) collected at the Mauna Loa Observatory in Hawaii, between 1958 and 2001. The objective is to model the CO2 concentration as a function of the time *t* and extrapolate for years after 2001.


### Build the dataset

We will derive a dataset from the Mauna Loa Observatory that collected air samples. We are interested in estimating the concentration of CO2 and extrapolate it for further year. First, we load the original dataset available in OpenML.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
from sklearn.datasets import fetch_openml

co2 = fetch_openml(data_id=41187, as_frame=True, parser="pandas")
co2.frame.head()
~~~
</div>
First, we process the original dataframe to create a date index and select only the CO2 column.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
import pandas as pd

co2_data = co2.frame
co2_data["date"] = pd.to_datetime(co2_data[["year", "month", "day"]])
co2_data = co2_data[["date", "co2"]].set_index("date")
co2_data.head()
~~~
</div>
<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
co2_data.index.min(), co2_data.index.max()
~~~
</div>
Out: `(Timestamp('1958-03-29 00:00:00'), Timestamp('2001-12-29 00:00:00'))`

We see that we get CO2 concentration for some days from March, 1958 to December, 2001. We can plot these raw information to have a better understanding.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
import matplotlib.pyplot as plt

co2_data.plot()
plt.ylabel("CO$_2$ concentration (ppm)")
_ = plt.title("Raw air samples measurements from the Mauna Loa Observatory")
~~~
</div>

We will preprocess the dataset by taking a monthly average and drop month for which no measurements were collected. Such a processing will have an smoothing effect on the data.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
co2_data = co2_data.resample("M").mean().dropna(axis="index", how="any")
co2_data.plot()
plt.ylabel("Monthly average of CO$_2$ concentration (ppm)")
_ = plt.title(
    "Monthly average of air samples measurements\nfrom the Mauna Loa Observatory"
)
~~~
</div>
The idea in this example will be to predict the CO2 concentration in function of the date. We are as well interested in extrapolating for upcoming year after 2001.

As a first step, we will divide the data and the target to estimate. The data being a date, we will convert it into a numeric.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
X = (co2_data.index.year + co2_data.index.month / 12).to_numpy().reshape(-1, 1)
y = co2_data["co2"].to_numpy()
~~~
</div>

### Design the proper kernel

To design the kernel to use with our Gaussian process, we can make some assumption regarding the data at hand. We observe that they have several characteristics: we see a long term rising trend, a pronounced seasonal variation and some smaller irregularities. We can use different appropriate kernel that would capture these features.

First, the long term rising trend could be fitted using a radial basis function (RBF) kernel with a large length-scale parameter. The RBF kernel with a large length-scale enforces this component to be smooth. An trending increase is not enforced as to give a degree of freedom to our model. The specific length-scale and the amplitude are free hyperparameters.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
from sklearn.gaussian_process.kernels import RBF

long_term_trend_kernel = 50.0**2 * RBF(length_scale=50.0)
~~~
</div>

The seasonal variation is explained by the periodic exponential sine squared kernel with a fixed periodicity of 1 year. The length-scale of this periodic component, controlling its smoothness, is a free parameter. In order to allow decaying away from exact periodicity, the product with an RBF kernel is taken. The length-scale of this RBF component controls the decay time and is a further free parameter. This type of kernel is also known as locally periodic kernel.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
from sklearn.gaussian_process.kernels import ExpSineSquared

seasonal_kernel = (
    2.0**2
    * RBF(length_scale=100.0)
    * ExpSineSquared(length_scale=1.0, periodicity=1.0, periodicity_bounds="fixed")
)
~~~
</div>

The small irregularities are to be explained by a rational quadratic kernel component, whose length-scale and alpha parameter, which quantifies the diffuseness of the length-scales, are to be determined. A rational quadratic kernel is equivalent to an RBF kernel with several length-scale and will better accommodate the different irregularities.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
from sklearn.gaussian_process.kernels import RationalQuadratic

irregularities_kernel = 0.5**2 * RationalQuadratic(length_scale=1.0, alpha=1.0)
~~~
</div>

Finally, the noise in the dataset can be accounted with a kernel consisting of an RBF kernel contribution, which shall explain the correlated noise components such as local weather phenomena, and a white kernel contribution for the white noise. The relative amplitudes and the RBF’s length scale are further free parameters.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
from sklearn.gaussian_process.kernels import WhiteKernel

noise_kernel = 0.1**2 * RBF(length_scale=0.1) + WhiteKernel(
    noise_level=0.1**2, noise_level_bounds=(1e-5, 1e5)
)
~~~
</div>

Thus, our final kernel is an addition of all previous kernel.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
co2_kernel = (
    long_term_trend_kernel + seasonal_kernel + irregularities_kernel + noise_kernel
)
co2_kernel
~~~
</div>

Out: `50**2 * RBF(length_scale=50) + 2**2 * RBF(length_scale=100) * ExpSineSquared(length_scale=1, periodicity=1) + 0.5**2 * RationalQuadratic(alpha=1, length_scale=1) + 0.1**2 * RBF(length_scale=0.1) + WhiteKernel(noise_level=0.01)`

### Model fitting and extrapolation

Now, we are ready to use a Gaussian process regressor and fit the available data. To follow the example from the literature, we will subtract the mean from the target. We could have used normalize_y=True. However, doing so would have also scaled the target (dividing y by its standard deviation). Thus, the hyperparameters of the different kernel would have had different meaning since they would not have been expressed in ppm.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
from sklearn.gaussian_process import GaussianProcessRegressor

y_mean = y.mean()
gaussian_process = GaussianProcessRegressor(kernel=co2_kernel, normalize_y=False)
gaussian_process.fit(X, y - y_mean)
~~~
</div>

`GaussianProcessRegressor(kernel=50**2 * RBF(length_scale=50) + 2**2 * RBF(length_scale=100) * ExpSineSquared(length_scale=1, periodicity=1) + 0.5**2 * RationalQuadratic(alpha=1, length_scale=1) + 0.1**2 * RBF(length_scale=0.1) + WhiteKernel(noise_level=0.01))`

Now, we will use the Gaussian process to predict on:

training data to inspect the goodness of fit;

future data to see the extrapolation done by the model.

Thus, we create synthetic data from 1958 to the current month. In addition, we need to add the subtracted mean computed during training.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
import datetime
import numpy as np

today = datetime.datetime.now()
current_month = today.year + today.month / 12
X_test = np.linspace(start=1958, stop=current_month, num=1_000).reshape(-1, 1)
mean_y_pred, std_y_pred = gaussian_process.predict(X_test, return_std=True)
mean_y_pred += y_mean
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python
plt.plot(X, y, color="black", linestyle="dashed", label="Measurements")
plt.plot(X_test, mean_y_pred, color="tab:blue", alpha=0.4, label="Gaussian process")
plt.fill_between(
    X_test.ravel(),
    mean_y_pred - std_y_pred,
    mean_y_pred + std_y_pred,
    color="tab:blue",
    alpha=0.2,
)
plt.legend()
plt.xlabel("Year")
plt.ylabel("Monthly average of CO$_2$ concentration (ppm)")
_ = plt.title(
    "Monthly average of air samples measurements\nfrom the Mauna Loa Observatory"
)
~~~
</div>

Our fitted model is capable to fit previous data properly and extrapolate to future year with confidence.

### Interpretation of kernel hyperparameters

Now, we can have a look at the hyperparameters of the kernel.

`gaussian_process.kernel_`

Out: `44.8**2 * RBF(length_scale=51.6) + 2.64**2 * RBF(length_scale=91.5) * ExpSineSquared(length_scale=1.48, periodicity=1) + 0.536**2 * RationalQuadratic(alpha=2.89, length_scale=0.968) + 0.188**2 * RBF(length_scale=0.122) + WhiteKernel(noise_level=0.0367)`

Thus, most of the target signal, with the mean subtracted, is explained by a long-term rising trend for ~45 ppm and a length-scale of ~52 years. The periodic component has an amplitude of ~2.6ppm, a decay time of ~90 years and a length-scale of ~1.5. The long decay time indicates that we have a component very close to a seasonal periodicity. The correlated noise has an amplitude of ~0.2 ppm with a length scale of ~0.12 years and a white-noise contribution of ~0.04 ppm. Thus, the overall noise level is very small, indicating that the data can be very well explained by the model.

**Total running time of the script:** ( 0 minutes 8.782 seconds)

<!-- Template code block

<div class="alert alert-secondary" role="alert" markdown="1">

~~~Python

~~~
</div>

-->

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>

This chapter used and modified material from [Gaussian process regression (GPR) on Mauna Loa CO2 data](https://scikit-learn.org/stable/auto_examples/gaussian_process/plot_gpr_co2.html).

Authors: 
- Jan Hendrik Metzen <jhm@informatik.uni-bremen.de>
- Guillaume Lemaitre <g.lemaitre58@gmail.com>

License: BSD 3 clause
</div>


{% include next-button.html 
           top-label="Staging and File System Choice ->" 
           bottom-label="3:20pm" 
           url="/morea/hpc/experience-hpc-file-systems.html" %}
