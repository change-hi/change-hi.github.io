---
title: "3. Launch a Jupyter Lab in Open OnDemand"
published: true
morea_id: experience-hpc-jupyter
morea_type: experience
morea_summary: "Requesting computing resources on Mana"
morea_sort_order: 4
morea_labels:
  - 2:30pm
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How to ask for computing resources?
* Why use Jupyter labs and notebooks?

**Objectives**
* Request resources on Mana.
* Start a jupyter lab session with Open OnDemand.
</div>

### Download the workshop Jupyter notebook

If you haven't already, please download [participants-copy-2022.ipynb](code/participants-copy-2022.ipynb) to your local computer (use "save as", i.e. right click).

## Review: Jupyter Lab as an Interactive Application in Open OnDemand

As we previously saw, Open OnDemand allows us to use interactive applications, one of which is Juypter Lab.

{% include figure.html url="" max-width="50%"
file="/morea/hpc/fig/ood_form.png"
alt="Connect to cluster" caption="" %}

The form is used to specify what resources you want, which are then placed into a queue with other waiting jobs and will start to run your job  as soon as the resources requested are available.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Under the hood**
<hr/>

The Open On Demand form for interactive applications defines a job script and passes it to the HPC systems job scheduler, taking the burden of how to start the application on the HPC system and how to write a job script that the job scheduler can understand off of the user.

</div>

## Activity: Learn to start a session

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Startup Jupyter Lab and Open Jupyter**
<hr/>

As we will be working in Jupyter Lab to explore some concepts when working with HPC systems and deep learning, your challenge is to start an interactive application of Jupyter Lab with the following parameters:

* **Partition:** workshop
* **Number of hours:** 3
* **Number of Nodes**: 1
* **Number of Tasks per Node**: 1
* **Number of cores per task:** 4
* **GB of Ram:** 24 GB
* **Number of GPUs requested:** 1
* **GPU Type:** Any

Once the interactive session is running, connect to the jupyter session by click the "Connect to Jupyter" button.

<details>
  <summary>Solution</summary>
{% include figure.html url="" max-width="100%" file="/morea/hpc/fig/ood_job.png" alt="Connect to cluster" caption="" %}
</details>
</div>

## Why use Jupyter?

For Python-based data science and machine learning applications, Jupyter notebook is a great platform because:

1. You can store your data, code, do visualizations, equations, text, outputs all in one place,
2. You can easily share your work easily in different formats like JSON, PDF, html,
3. It supports more than 40 programming languages, can switch between differnt environments and has an interactive output,
4. You can easily edit the code and re-run it without affecting other sections.

### Jupyter Lab vs Jupyter Notebook

Jupyter notebook allows you to access ipython notebooks only (.ipynb files), i.e. it will create a computational environment which stores your code, results, plots, texts etc. And here you can work in only one of your environments. 

Jupyter Lab gives a better user interface along with all the facilties provided by the notebook. It is a flexible, web based application with a modular structure where one can access  python files (.py), ipython notebooks, html or markdown files, access file browser (to upload, download, copy, rename, delete files), work with multiple Jupyter notebooks and environments, all in the same window. 

To use Jupyter Lab, You write your code or plain text in rectangular “cells” and the browser then passes it to the back-end “kernel”, which runs your code and returns output.

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-triangle-exclamation fa-xl"></i> **Heads up: file extensions!**
<hr/>

Note the difference between file extensions: .ipynb file is a python notebook which stores code, text, markdown, plots, results in a specific  format but .py file is a python file which only stores code and plain text (like comments etc).

</div>

{% include next-button.html 
           top-label="Install Modules and Setup an Environment ->" 
           bottom-label="2:40pm" 
           url="/morea/hpc/experience-hpc-environment.html" %}
