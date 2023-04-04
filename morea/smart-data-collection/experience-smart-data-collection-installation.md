---
title: "3. Installing Jupyter Libraries"
published: true
morea_id: experience-smart-data-collection-installation
morea_type: experience
morea_summary: "How do we access Tapis using a Jupyter notebook within MANA?"
morea_sort_order: 2
morea_labels:
  - 2:30 - 2:45pm
---

# 3. Installing Tapis Libraries

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
  * How do we bring Tapis libraries into our Jupyter notebook?

**Objectives**
  * Open the HPC terminal in the browser.
  * Use pip to install python libraries.
  * Import libraries and test them out in a Jupyter notebook.
</div>

## Open a terminal

First we'll want to open a terminal on the node that our notebook is running on.
To do this, go to the tab where you opened the notebook from, and click "New".

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_home_new_outlined.png" alt="Connect to cluster" caption="" %}

Next, click "Terminal" from the drop-down bar.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_home_new_terminal_outlined.png" alt="Connect to cluster" caption="" %}

You should now be brought to a terminal connected to the virtual machine.

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-triangle-exclamation fa-xl"></i> **Heads up!**
<hr/>

On your first time using a MANA terminal, it will show a "do you trust this system" prompt, simply type "yes" and enter.
</div>


{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_terminal_start.png" alt="Connect to cluster" caption="" %}

Now that we have a terminal, it's time to install some python packages!

## Install tapipy

Let's install the `tapipy` package, which includes functions that help us work with the Tapis system.

Run the following command:

```bash
python -m pip install tapipy
```

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **What this does...**
<hr/>
This runs python and tells it to execute the "pip" module, then tells pip to install tapipy.
</div>

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_terminal_install_tapipy.png" alt="Connect to cluster" caption="" %}



When it's done, you should see the following:

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_terminal_installed_tapipy.png" alt="Connect to cluster" caption="" %}


## Get a sample notebook

We're going to use `git` to download the latest version of the Jupyter Notebook for this workshop.
Git is an application that helps with collaborative software development.
Its `clone` command allows us to download the entire project folder (called a Repository) in a simple and reproducible manner.

Run the following command:

```bash
git clone https://github.com/CI-TRACS/Smart-Data_Collection_for_sensor_networks_notebook.git
```

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_terminal_clone_notebook.png" alt="Connect to cluster" caption="" %}


It will take a few seconds to load, then you should see the following.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_terminal_cloned_notebook.png" alt="Connect to cluster" caption="" %}


Now, let's get to editing the notebook!

## Open the notebook for editing

Now that we've cloned the notebook repository to the `~/Smart-Data_collection_for_sensor_networks_notebook` directory, it's time to go there and open up the notebook.

Go back to the Jupyter Home interface, where you should see a screen like this:

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_home_with_notebook.png" alt="Connect to cluster" caption="" %}


Click `Smart-Data_Collection_for_sensor_networks_notebook` to enter our newly downloaded folder.

The new folder includes our notebook, and any other files we will happen to need.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/jupyter_file_manager_in_notebook_repo.png" alt="Connect to cluster" caption="" %}

Finally, click the `Smart-Data_Collection_for_sensor_networks.ipynb` file to open our notebook.

The notebook should now be open, and ready to edit!

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/notebook_open.png" alt="Connect to cluster" caption="" %}

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

* MANA’s web interface provides a terminal for the machine that the notebook runs on.
* You can install and import new python libraries to support a notebook.
</div>


<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Bio Break!**
<hr/>

Let's take a brief break to stretch before moving on to the next page.  See you in a few minutes.
</div>

{% include next-button.html
top-label="4. Tapis Streams ->"
bottom-label="2:45pm"
url="/morea/smart-data-collection/experience-smart-data-collection-tapis-streams.html" %}
