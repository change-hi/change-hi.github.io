---
title: "2. Connecting to Jupyter"
published: true
morea_id: experience-smart-data-collection-jupyter
morea_type: experience
morea_summary: "How do we deploy and access a Jupyter notebook server using MANA?"
morea_sort_order: 2
morea_labels:
  - 2:15 - 2:30pm
morea_enable_toc: true
---

# 2. Connecting to Jupyter

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
  * How do we deploy and access a Jupyter notebook server using MANA?

**Objectives**
  * Use MANA’s web interface to deploy a Jupyter notebook server job and connect to the server.
</div>

## Creating a Jupyter notebook server

We will use MANA to deploy and access a Jupyter notebook with python scripts demonstrating the usage of the Tapis Streams API. The web interface for MANA includes a built in interface for creating and deploying a Jupyter notebook server.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Note**
<hr/>
If you are already familiar with an alternative method to deploy a Jupyter notebook, e.g. Google Colab, feel free to use that instead.
</div>

### Deploying a Jupyter notebook server on MANA

Go to [https://uhhpc.its.hawaii.edu/](https://uhhpc.its.hawaii.edu/){:target="_blank"} in a web browser and log in with your UH credentials. This will bring you to the MANA web interface.

At the top of this interface there should be a dropdown menu labeled "Interactive Apps". Click this and select "Jupyter Notebook" from the dropdown menu. This will bring you to a form for configuring and deploying the server as a job on MANA.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/mana_jupyter.PNG" alt="Connect to cluster" caption="" %}


We will deploy this job to the workshop partition. Most of the default settings for this job should work, but increase the "Number of hours" to 2. These values should be as follows:

| Field                     | Value       |
| ------------------------- | ----------- |
| SLURM Account             | (blank)     |
| Partition                 | workshop    |
| Number of hours           | 2           |
| Number of cores           | 1           |
| GB of RAM                 | 6           |
| Number of GPUs requested  | 0           |
| GPU Type                  | Any         |
{: .table }

Click the "Launch" button to schedule the job. This should display a tile with information about the job including its status. The job will likely start with the "Queued" status indicating that it has been queued and is waiting for resources to become available to execute the job.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/job_queued.PNG" alt="Connect to cluster" caption="" %}

Shortly, the job status should change to "Running" indicating the job has been launched, and a "Connect to Jupyter" button should be available at the bottom of the tile. Clicking this will connect you to the deployed Jupyter notebook server.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/job_running.PNG" alt="Connect to cluster" caption="" %}


The Jupyter notebook server will display the files available in your account's home directory on MANA. We will need to download the notebook file for this workshop and install some dependencies the notebook relies on. The next section will describe how to install these dependencies and load the notebook.

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

* MANA’s web interface provides a built in function for deploying a Jupyter notebook server.
* After configuring and submitting a job to MANA for deploying the Jupyter notebook server, we can connect to the server and use it to access notebook files stored in the user’s home directory.
</div>


{% include next-button.html
top-label="3. Installing Tapis Libraries ->"
bottom-label="2:30pm"
url="/morea/smart-data-collection/experience-smart-data-collection-installation.html" %}
