---
title: "2. Plotly Tutorial"
published: true
morea_id: experience-plotly-tutorial
morea_type: experience
morea_summary: "Understand Plotly implementation basics"
morea_sort_order: 3
morea_labels:
  - 2:30pm
---

# 2. Plotly Tutorial

<div class="alert alert-info mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Objectives**
* Give you a comprehensive overview of Plot.ly and its benefits over other similar statistical visualization tools.
* Demonstrate the simplicity of creating Plot.ly charts.
</div>

Plot.ly is a library (application programming interface) for  creating high quality charts. Plotly has an immensely rich collection of chart types, all of which are interactive. Another popular charting library is [Matplotlib](https://matplotlib.org/). Whereas Matplotlib only supports Python, Plotly supports Javascript, Python, as well as R. At its core, Plot.ly's graphics are created in [D3.js](https://d3js.org/).

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/plotly.png" alt="plotly" caption="" %}


Chart Studio is a web-based tool that allows you to create charts and simple dashboards using Plot.ly, eliminating the need for coding skills. Additionally, charts created in Chart Studio can be exported to either Javascript or Python code, making it an excellent tool for learning and exploration.

{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/chartstudio.png" alt="plotly" caption="" %}

Dash is a Python library for making web-based interactive visualization dashboards of Plot.ly charts. Often to create web-based dashboards you need to code the frontend in Javascript. Dash allows you to do everything in Python.

The best place to go to begin learning is Plotly's [main library page](https://plotly.com/graphing-libraries/), which will then direct you to tutorials for Plotly in [Python](https://plotly.com/python/), [R](https://plotly.com/r/), [Javascript](https://plotly.com/javascript/), as well as [Dash](https://dash.plotly.com/).

Go to the main library page and take a look at either Plotly Python or Plotly Javascript then select one of the basic charts to look at the respective codes. Also take a look at Dash example [galleries](https://dash.gallery/Portal/).

Note: for Plotly Python there are two ways to use Plotly. I recommend most users use Plotly Express (which is a very low-code library to Plotly's most common charts). Most of the examples you will find use Plotly Express. For advanced needs you can learn to use [Plotly Graph Objects](https://plotly.com/python/graph-objects/).

As an example of how easy it is to create charts in Plotly Express here are the lines of code you need to make a scatterplot:

<div class="alert alert-secondary mt-3" role="alert" markdown="1">
~~~python
import plotly.express as px
fig = px.scatter(x=[0, 1, 2, 3, 4], y=[0, 1, 4, 9, 16])
fig.show()
~~~

{% include figure.html url="" max-width="60%" file="/morea/data-visualization/fig/scatter.png" alt="plotly" caption="" %}
</div>

And if you are familiar with using Pandas for data wrangling, here's an example of a scatterplot by first reading a data file into a Pandas data frame:

<div class="alert alert-secondary mt-3" role="alert" markdown="1">
~~~python
import plotly.express as px
import pandas as pd

csv_url = 'https://archive.ics.uci.edu/ml/machine-learning-databases/iris/iris.data'

# using the attribute information as the column names
col_names = ['sepal_length','sepal_width','petal_length','petal_width','species']

df =  pd.read_csv(csv_url, names = col_names)

fig = px.scatter(df, x="sepal_width", y="sepal_length")
fig.show()
~~~
{% include figure.html url="" max-width="60%" file="/morea/data-visualization/fig/scatterpandas.png" alt="plotly" caption="" %}
</div>

And if you replaced:

<div class="alert alert-secondary mt-3" role="alert" markdown="1">
~~~python
fig = px.scatter(df, x="sepal_width", y="sepal_length")
~~~
</div>

with

<div class="alert alert-secondary mt-3" role="alert" markdown="1">
~~~python
fig = px.scatter_matrix(df, dimensions=["sepal_width", "sepal_length", "petal_width", "petal_length"], color="species"
~~~
</div>

You can get this scatterplot matrix:
{% include figure.html url="" max-width="80%" file="/morea/data-visualization/fig/scattermatrix.png" alt="plotly" caption="" %}


Lastly, should you venture into creating Dash dashboards, and wish to make them publicly viewable, you will need to host a Python server.
An easy way to do this is to use [Pythonanywhere](https://www.pythonanywhere.com/).


Here is a video illustrating how to do this.

{% include youtube.html id="0JJ8cM2fcac" %}

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>
* Plot.ly is a popular statistical visualization library that works in multiple programming languages including Python, Javascript, and R
* Easier to code with Plot.ly
* <strong>`Chart Studio`</strong> can be used to produce Plot.ly charts and dashboards without coding
* <strong>`Dash`</strong> allows for creation of visualizations and dashboards using only Python.
</div>


{% include next-button.html 
           top-label="3. Paraview Tutorial ->" 
           bottom-label="2:45pm" 
           url="/morea/data-visualization/experience-paraview-tutorial.html" %}
