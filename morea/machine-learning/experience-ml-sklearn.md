---
title: "2. Scikit-Learn"
published: true
morea_id: experience-ml-sklearn
morea_type: experience
morea_summary: "A basic Scikit-learn tutorial using Gaussian Processes to model CO2 levels on Mauna Loa"
morea_sort_order: 10
morea_labels:
  - 2:05pm - 2.55pm
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How can we model environmental data with decision trees?

**Objectives**
* Understand how to fit decision trees in SciKit-Learn
</div>

<a target="_blank" href="https://colab.research.google.com/github/AmilaIndika789/change-hi.github.io/blob/1_sklearn/morea/machine-learning/Notebooks/01-scikit-learn-climate-example.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

# Decision Trees on Mauna Loa CO2 data

This example uses data that consists of the monthly average atmospheric CO2 concentrations (in parts per million by volume (ppm)) collected at the Mauna Loa Observatory in Hawaii, between 1958 and 2001. The objective is to model the CO2 concentration as a function of the time *t*.


### Build the dataset

We will derive a dataset from the Mauna Loa Observatory that collected air samples. We are interested in estimating the concentration of CO2 and extrapolate it for further year. First, we load the original dataset available in OpenML.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
from sklearn.datasets import fetch_openml

co2 = fetch_openml(data_id=41187, as_frame=True, parser="pandas")
co2.frame.head()
~~~
</div>

First, we process the original dataframe to create a date index and select only the CO2 column.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
import pandas as pd

# Do necessary data type conversion and extract only required columns
co2_data = co2.frame
co2_data["date"] = pd.to_datetime(co2_data[["year", "month", "day"]])
co2_data = co2_data[["date", "co2"]].set_index("date")
co2_data.head()
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
co2_data.index.min(), co2_data.index.max()
~~~
</div>
Out: `(Timestamp('1958-03-29 00:00:00'), Timestamp('2001-12-29 00:00:00'))`

We see that we get CO2 concentration for some days from March, 1958 to December, 2001. We can plot these raw information to have a better understanding.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
import matplotlib.pyplot as plt

co2_data.plot()
plt.ylabel("CO$_2$ concentration (ppm)")
_ = plt.title("Raw air samples measurements from the Mauna Loa Observatory")
~~~
</div>
{% include figure.html url="" max-width="60%" file="morea/machine-learning/fig/co2_data.png" alt="Basic Binder Webpage" caption="" %}

We will preprocess the dataset by taking a monthly average and drop month for which no measurements were collected. Such a processing will have an smoothing effect on the data.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
# Resample data monthly
co2_data = co2_data.resample("M").mean().dropna(axis="index", how="any")
~~~
</div>

**Cross validation** is an important step in machine learning. In cross validation, the machine learning model is trained and evaluated on different subsets of input data. This step is crucial for clean evaluation, increased generalizability, and minimize underfitting & overfitting.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
from sklearn.model_selection import train_test_split

RANDOM_SEED = 42  # Ensures reproducibility of split
co2_train, co2_validation = train_test_split(
    co2_data, test_size=0.25, shuffle=False, random_state=RANDOM_SEED
)
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
plt.plot(co2_train)
plt.plot(co2_validation)
plt.ylabel("Monthly average of CO$_2$ concentration (ppm)")
plt.xlabel("Date")
_ = plt.title(
    "Monthly average of air samples measurements\nfrom the Mauna Loa Observatory"
)
plt.legend(["train", "validation"])
~~~
</div>

{% include figure.html url="" max-width="60%" file="morea/machine-learning/fig/co2_data_smoothed.png" alt="Basic Binder Webpage" caption="" %}

The idea in this example will be to predict the CO2 concentration in function of the date. We are as well interested in extrapolating for upcoming year after 2001.

As a first step, we will divide the data and the target to estimate. The data being a date, we will convert it into a numeric.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
X = (co2_train.index.year + co2_train.index.month / 12).to_numpy().reshape(-1, 1)
y = co2_train["co2"].to_numpy()
~~~
</div>

### Model fitting using Decision Tree Regression

Decision Trees (DTs) are a non-parametric supervised learning method used for classification and regression. The goal is to create a model that predicts the value of a target variable by learning simple decision rules inferred from the data features. A tree can be seen as a piecewise constant approximation.

Decision trees learn from data to approximate a function with a set of if-then-else decision rules. The deeper the tree, the more complex the decision rules. Deeper trees are more powerful, but this can lead to overfitting.

{% include figure.html url="" max-width="60%" file="morea/machine-learning/fig/decision_trees.jpg" alt="Basic Binder Webpage" caption="Image from https://dinhanhthi.com/decision-tree-regression/" %}


<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
from sklearn import tree

# Train models
decision_tree_1 = tree.DecisionTreeRegressor(max_depth=2)
decision_tree_2 = tree.DecisionTreeRegressor(max_depth=11)
decision_tree_1.fit(X, y)
decision_tree_2.fit(X, y)
~~~
</div>

Next, we evaluate the performance on the validation data.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
# Make predictions on validation data
X_validation = (
    (co2_validation.index.year + co2_validation.index.month / 12)
    .to_numpy()
    .reshape(-1, 1)
)
y_validation = co2_validation["co2"].to_numpy()

y_predictions_1 = decision_tree_1.predict(X_validation)
y_predictions_2 = decision_tree_2.predict(X_validation)
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
from sklearn.metrics import mean_squared_error

# Calculate evaluation metrics
mse_of_regr_1 = mean_squared_error(y_validation, y_predictions_1)
mse_of_regr_2 = mean_squared_error(y_validation, y_predictions_2)

print(f"Validation MSE for Decision Tree with depth 2: {mse_of_regr_1:.4f}")
print(f"Validation MSE for Decision Tree with depth 11: {mse_of_regr_2:.4f}")
~~~
</div>
Out: <br>
`Validation MSE for Decision Tree with depth 2: 210.6841` <br>
`Validation MSE for Decision Tree with depth 11: 96.5067`

Now, we will use the the fitted models to predict on:

* training data to inspect the goodness of fit;

* validation data to inspect the generalizability;

* future data to see the extrapolation done by the models.

Thus, we create synthetic data from 1958 to the current month. 

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
import datetime
import numpy as np

# Get dates from 1958 to 2023
today = datetime.datetime.now()
current_month = today.year + today.month / 12
X_test = np.linspace(start=1958, stop=current_month, num=1_000).reshape(-1, 1)
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
# Make predictions
y_1 = decision_tree_1.predict(X_test)
y_2 = decision_tree_2.predict(X_test)
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
plt.figure(figsize=(10, 6))
plt.scatter(X, y, s=20, edgecolor="black", c="darkorange", label="data")

# Plot predictions of decision tree 1
plt.plot(X_test, y_1, color="cornflowerblue", label=f"max_depth={decision_tree_1.max_depth}", linewidth=2)

# Plot predictionso f decision tree 2
plt.plot(X_test, y_2, color="yellowgreen", label=f"max_depth={decision_tree_2.max_depth}", linewidth=2)

plt.xlabel("data")
plt.ylabel("target")
plt.title("Decision Tree Regression")
plt.legend()
plt.show()
~~~
</div>
{% include figure.html url="" max-width="60%" file="morea/machine-learning/fig/co2_decision_trees.png" alt="Basic Binder Webpage" caption="" %}

As you can see, the decision tree regression was able to fit data within the existing domain quite well. The criteria for decisions is intuitive and can be understood with a simple visualization. However, it has completely failed to predict any future trend outside the domain it was trained on.

### Model the derivative of the data

To improve the model's generalization, we will predict on differences in CO2 rather than absolute CO2 levels, using a "sliding window" of recent CO2 differences as the input. 
We will also normalize the data.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
def preprocess_data(input_data, train_window, scaler, forecast_window=1, is_test=False):
    """
    Function that takes data and reformat for the autoregressive task
    """

    # Take derivative
    input_data = np.concatenate([[0], np.diff(input_data)])

    # Scale values
    scaler = scaler

    # Important: Not to leak information from training data to test data (clean evaluation)
    if is_test:
        normalized_data = scaler.transform(input_data.reshape(-1, 1)).reshape(-1)
    else:
        normalized_data = scaler.fit_transform(input_data.reshape(-1, 1)).reshape(-1)

    # Create input-output pairs
    in_seq = []
    out_seq = []
    L = len(normalized_data)

    # Reformat training data for autoregressive task
    for i in range(0, L - train_window - forecast_window, forecast_window):
        train_seq = normalized_data[i : i + train_window]
        train_label = normalized_data[
            i + train_window : i + train_window + forecast_window
        ]

        in_seq.append(train_seq)
        out_seq.append(train_label)

    return normalized_data, in_seq, out_seq, scaler
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
from sklearn.preprocessing import StandardScaler

# Paramters
TRAIN_WINDOW = 50  # No of months looked back
FORECAST_WINDOW = 1  # No of months predicted forward
standardScaler = StandardScaler()

# Create training data for autoregrssive task
normalized_train, X_train, y_train, scaler = preprocess_data(
    list(co2_train["co2"]),
    TRAIN_WINDOW,
    standardScaler,
    forecast_window=FORECAST_WINDOW,
    is_test=False,
)
~~~
</div>


We will train 3 decision trees at different max depths.

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
# Train models
decistion_tree_3 = tree.DecisionTreeRegressor(max_depth=2)
decistion_tree_3.fit(X_train, y_train)

decision_tree_4 = tree.DecisionTreeRegressor(max_depth=10)
decision_tree_4.fit(X_train, y_train)

decision_tree_5 = tree.DecisionTreeRegressor(max_depth=25)
decision_tree_5.fit(X_train, y_train)
~~~
</div>

Next, we will evaluate trained decision trees on the validation data.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
# Create validation data for autoregrssive task
normalized_test, X_validation, y_validation, _ = preprocess_data(
    list(co2_validation["co2"]),
    TRAIN_WINDOW,
    standardScaler,
    forecast_window=FORECAST_WINDOW,
    is_test=True,
)

# Make predictions on validation data
y_predictions_3 = decistion_tree_3.predict(X_validation)
y_predictions_4 = decision_tree_4.predict(X_validation)
y_predictions_5 = decision_tree_5.predict(X_validation)
~~~
</div>

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
# Calculate evaluation metrics
mse_of_decision_tree_3 = mean_squared_error(y_validation, y_predictions_3)
mse_of_decision_tree_4 = mean_squared_error(y_validation, y_predictions_4)
mse_of_decision_tree_5 = mean_squared_error(y_validation, y_predictions_5)

print(f"Validation MSE for Decision Tree with depth 2: {mse_of_decision_tree_3:.4f}")
print(f"Validation MSE for Decision Tree with depth 10: {mse_of_decision_tree_4:.4f}")
print(f"Validation MSE for Decision Tree with depth 25: {mse_of_decision_tree_5:.4f}")
~~~
</div>
Out: <br>
`Validation MSE for Decision Tree with depth 2: 0.1530` <br>
`Validation MSE for Decision Tree with depth 10: 0.1828` <br>
`Validation MSE for Decision Tree with depth 25: 0.1621`

Now we will generate test data that runs all the way to the present day to see the model's predictions. We use the model's own prediction as part of the sliding window for the next prediction, to extrapolate arbitrarily far into the future.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
dates = pd.period_range("1958", "2023", freq="M").to_timestamp()

test_inputs = list(normalized_train)
future_predictions_3 = test_inputs.copy()
future_predictions_4 = test_inputs.copy()
future_predictions_5 = test_inputs.copy()

# Make predictions on validation data
future_predictions_count = len(dates) - len(test_inputs)

# Iteratively make predictions by moving the training window forward
for i in range(future_predictions_count):
    seq = future_predictions_3[-TRAIN_WINDOW:]
    prediction = decistion_tree_3.predict([seq])
    future_predictions_3.append(prediction[0])

    seq = future_predictions_4[-TRAIN_WINDOW:]
    prediction = decision_tree_4.predict([seq])
    future_predictions_4.append(prediction[0])

    seq = future_predictions_5[-TRAIN_WINDOW:]
    prediction = decision_tree_5.predict([seq])
    future_predictions_5.append(prediction[0])
~~~
</div>

Let's plot the results. Note that it is still showing the differences (derivative) rather than the absolute value, and it's still normalized.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
plt.figure(figsize=(10, 6))

# Plots of derivative predictions
plt.plot(dates, future_predictions_3, label=f"max_depth={decistion_tree_3.max_depth}", linewidth=2)
plt.plot(dates, future_predictions_4, label=f"max_depth={decision_tree_4.max_depth}", linewidth=2)
plt.plot(dates, future_predictions_5, label=f"max_depth={decision_tree_5.max_depth}", linewidth=2)
plt.plot(dates[0:len(normalized_train)], normalized_train, label=f"true value", linewidth=2)

plt.xlabel("data")
plt.ylabel("target")
plt.title("Decision Tree Regression on Derivative")
plt.legend()
plt.show()
~~~
</div>

{% include figure.html url="" max-width="60%" file="morea/machine-learning/fig/co2_decision_tree_derivative.png" alt="Basic Binder Webpage" caption="" %}

We can see that all of the decision trees are fitting the past data nearly perfectly, but do not entirely agree on future predictions.

Let's convert the predictions back into absolute CO2 levels.
<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
def postprocess_data(output_data, scaler, first_input):
    """
    Function to convert CO2 differences back to absolute CO2 levels
    """
    # Unscale the output
    output = scaler.inverse_transform(np.array(output_data).reshape(-1, 1)).reshape(-1)

    # Get cumulative sum
    output = np.cumsum(output) + first_input

    return output

# Post process data
decoded_3 = postprocess_data(future_predictions_3, scaler, list(co2_data["co2"])[0])
decoded_4 = postprocess_data(future_predictions_4, scaler, list(co2_data["co2"])[0])
decoded_5 = postprocess_data(future_predictions_5, scaler, list(co2_data["co2"])[0])
~~~
</div>

And plot the results:

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python
plt.figure(figsize=(10, 6))

# Plot model outputs
plt.plot(dates, decoded_3, label=f"max_depth={decistion_tree_3.max_depth}", linewidth=2)
plt.plot(dates, decoded_4, label=f"max_depth={decision_tree_4.max_depth}", linewidth=2)
plt.plot(dates, decoded_5, label=f"max_depth={decision_tree_5.max_depth}", linewidth=2)

# Plot training and validation data
plt.plot(co2_train, label="train", linewidth=1)
plt.plot(co2_validation, label="validation", linewidth=1)

# Vertical dashed line to show the position of validation split
plt.axvline(co2_validation.index[0], linestyle="--", c="k")
plt.text(co2_validation.index[0], 320, "validation split", rotation=90)

# Vertical dashed line to show the position where future forecasts start
plt.axvline(co2_validation.index[-1], linestyle="--", c="k")
plt.text(co2_validation.index[-1], 320, "future forecasts start", rotation=90)

plt.xlabel("data")
plt.ylabel("target")
plt.title("Decision Tree Regression")
plt.legend()
plt.show()
~~~
</div>

{% include figure.html url="" max-width="60%" file="morea/machine-learning/fig/co2_decision_tree_final.png" alt="Basic Binder Webpage" caption="" %}

The results can vary quite a bit between runs. The method for fitting the decision trees is stochastic, and our many input variables are all similarly informative, so the tree's hierarchy can vary significantly. Decision trees are not robust, so slight changes in input or in the tree structure can drastically alter predictions.

<!-- Template code block

<div class="alert alert-secondary" role="alert" markdown="1">

~~~python

~~~
</div>

-->

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>

### Attribution: 
This workshop was modified from the following:

[Gaussian process regression (GPR) on Mauna Loa CO2 data](https://scikit-learn.org/stable/auto_examples/gaussian_process/plot_gpr_co2.html)

[Rasmussen, Carl Edward.
   "Gaussian processes in machine learning."
   Summer school on machine learning. Springer, Berlin, Heidelberg, 2003](http://www.gaussianprocess.org/gpml/chapters/RW.pdf).

Authors: 
- Jan Hendrik Metzen <jhm@informatik.uni-bremen.de>
- Guillaume Lemaitre <g.lemaitre58@gmail.com>

License: BSD 3 clause

[SciKit-Learn Decision Tree Regression tutorial](https://scikit-learn.org/stable/auto_examples/tree/plot_tree_regression.html)
[SciKit-Learn Decision Tree tutorial](https://scikit-learn.org/stable/modules/tree.html#decision-trees)
</div>


{% include next-button.html 
           top-label="Pytorch ->" 
           bottom-label="3:00pm" 
           url="/morea/machine-learning/experience-ml-pytorch.html" %}
