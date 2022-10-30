---
title: "4. Install Modules and Setup an Environment"
published: true
morea_id: experience-hpc-environment
morea_type: experience
morea_summary: "Create an environment and setup a Python kernel"
morea_sort_order: 5
morea_labels:
  - 2:40pm
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* What is an environment?
* How do we install software and modules on Mana?
* How do we create a Python kernel?

**Objectives**
* Create an environment with Anaconda.
* Install packages needed for deep learning tasks.
* Create a Python kernel.
</div>

## How to access and install software and modules?

### Use a package manager

Working with Python requires one to have different packages installed with a specific version which gets updated once in a while. On Mana, there are software packages already installed on the cluster which one can use to install the required libraries, softwares and can even choose which version to install.

You can use following commands to see what modules are available on the cluster or which ones are already loaded or to load a specific module in your environment:

```bash
module avail
module list 
module load <MODULE_NAME>
```

### So what is an environment then?

Sometimes different applications require different versions of the Python packages than the one you've been using and this is where a Python environment comes in handy.  

An environment (or a conda environment specifically, which we'll discuss later) is a directory, specific or isolated to a project, that contains a specific collection of python packages and their different versions that you have installed. There are 2 most popular tools to set up your environment:

1. Pip: a tool to install Python software packages only.

2. Anaconda (or Conda): cross platform package and environment manager which lets you access C, C++ libraries, R package for scientific computing along with Python.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note on packages**
<hr/>

Packages contains all the files you need for the modules it supplies
</div>

### The Anaconda package manager

This is a popular package manager in scientific computing which handles the Python and R programming language related dependencies rather easily. It is preferred more because:

* it has a clear directory structure which is easy to understand, 
* it allows you to install softwares written in any programming language, 
* it gives you a flexibility to create different environments with different software versions (and can install pip packages as well), 
* one can use both CLI and GUI.

{% include figure.html url="" max-width="50%" file="/morea/hpc/fig/Anaconda+Python.png" alt="Anaconda + Python" caption="" %}

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Environment isolation**
<hr/>

If you try to access a library with different version based on your project, pip may throw an error.
To create isolated environments, you can use virtual environment (venv) with pip.
</div>

### Activity: Learn how to setup an environment

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Load Anaconda and libraries**
<hr/>

First, create a conda environment:

```bash
module load lang/Anaconda3
conda create --name tf2
source activate tf2
```

Second, install relevant libraries:

```bash
conda install tensorflow-gpu matplotlib tensorflow keras
```
</div>

### Activity: Learn to create a Python kernel

Although we created a conda environment, the Jupyter notebook still cannot access it because "conda" is the directory that contains all the installed conda packages but it is the "kernel" that runs the user's code and can use and access different conda environments, if required.

A kernel is the computational engine that executes the code contained in Jupyter notebook or it is the interface which tells Jupyter notebook which kernel it should use to access the packages and softwares.

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Create an ipykernel**
<hr/>

Start up a python kernel:

```bash
conda install ipykernel
python -m ipykernel install --user --name tf2 --display-name tf2
```
</div>

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Bio Break!**
<hr/>
Let's take a brief break to stretch before moving on to the next page.  See you in a few minutes.
</div>

{% include next-button.html 
           top-label="Deep Learning Tutorial ->" 
           bottom-label="3:00pm" 
           url="/morea/hpc/experience-hpc-deep-learning.html" %}
