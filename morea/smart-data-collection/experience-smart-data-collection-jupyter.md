---
title: "2. Connecting to Jupyter"
published: true
morea_id: experience-smart-data-collection-jupyter
morea_type: experience
morea_summary: "How do we deploy and access a Jupyter notebook server using MANA?"
morea_sort_order: 2
morea_labels:
  - 15 min (Teaching)
morea_enable_toc: true
---

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

### Deploying a Jupyter notebook server on MANA

Go to [https://uhhpc.its.hawaii.edu/](https://uhhpc.its.hawaii.edu/) in a web browser and log in with your UH credentials. This will bring you to the MANA web interface.

At the top of this interface there should be a dropdown menu labeled "Interactive Apps". Click this and select "Jupyter Notebook" from the dropdown menu. This will bring you to a form for configuring and deploying the server as a job on MANA.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/mana_jupyter.PNG" alt="Connect to cluster" caption="" %}


We will deploy this job to the workshop partition. Most of the default settings for this job should work, but increase the "Number of hours" to 2. These values should be as follows:

| Syntax                    | Description |
| ------------------------- | ----------- |
| SLURM Account             |             |
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

## Key Points

<div class="alert alert-success" role="alert" markdown="1">

* MANA’s web interface provides a built in function for deploying a Jupyter notebook server.
* After configuring and submitting a job to MANA for deploying the Jupyter notebook server, we can connect to the server and use it to access notebook files stored in the user’s home directory.
</div>


<hr/>
For comparison purposes, here's the [Software Carpentry version of this page](https://ci-tracs.github.io/Smart-Data_Collection_for_sensor_networks/02-connecting_to_jupyter/index.html)
