---
title: "Setting Up Koa"
published: true
morea_id: reading-ssb-koa
morea_type: reading
morea_summary: "Create accounts on Koa, download sample file."
morea_sort_order: 1
morea_labels:
  - Pre-workshop
morea_enable_toc: true
---



<div class="alert alert-danger mt-3" role="alert" markdown="1">
<i class="fa-solid fa-circle-exclamation fa-xl"></i> **To be done during the workshop!**
<hr/>
Normally this reading would be done in advance of the workshop, but this semester, the instructors have elected to do it at the start of the workshop.

</div>

# Setting Up Koa

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Objectives**
  * Have an OOD compatible browser
  * Be able to connect to the workshop in Zoom and Koa Open OnDemand via a web browser
  * Download sample data
</div>

## Ensure you are using a compatible browser

Please make sure you have installed a compatible browser as specified at: <https://osc.github.io/ood-documentation/latest/requirements.html#browser-requirements>

## Connect to Koa through Open OnDemand

Connect to Koa by pointing your browser (ChromeOS, Firefox or Safari) at: <https://koa.its.hawaii.edu>

You should get the UH gold screen and then login with your user name and password.

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/gold_screen_crop.png" alt="Node anatomy" caption="" %}

Authenticate with MFA/DUO via your preferred method.

You should see the Koa Open OnDemand start page:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/koa_ood.png" alt="Node anatomy" caption="" %}

## Launch an interactive session on a compute node

Start an interactive session:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/select_desktop_koa.png" alt="Node anatomy" caption="" %}

Your input values should be:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/check_ignition_koa.png" alt="Node anatomy" caption="" %}

The output should look like this:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/waiting_for_a_session_koa.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/my_interactive_session_koa.png" alt="Node anatomy" caption="" %}

Click here to start a shell on node assigned to your Open Ondemand session:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/host_button_koa.png" alt="Node anatomy" caption="" %}

## Assign a compute node

You should see:
{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/koa_compute_shell.png" alt="Node anatomy" caption="" %}

If you see:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/are_you_sure.png" alt="Node anatomy" caption="" %}

Answer yes:

Warning: Permanently added ‘gpu-0016.hpc.ci.its.hawaii.edu,10.100.11.214’ (ECDSA) to the list of known hosts. Authentication failed. Your connection to the remote server has been terminated.

Go back to "my interactive sessions" in the browser and start another shell..

## Download sample files for this workshop

In your opened Desktop session which started a shell, copy and paste in the following commands below and then hit "enter" on your keyboard to download data-shell.zip within the `Desktop directory`. These set of commands are going to download and unzip the data-shell.zip file and create a folder called `data-shell` with several files and directories in it that will be used in this workshop. We'll learn more about these commands in this workshop. 

<div class="alert alert-secondary" role="alert" markdown="1">

```bash
cd Desktop
wget https://change-hi.github.io/morea/scientific-software-basics/data/data-shell.zip
unzip data-shell.zip
rm data-shell.zip
cd ..
```

</div>

To see if the files have been downloaded, copy and paste these commands into your shell:

<div class="alert alert-secondary" role="alert" markdown="1">

Input: 

```bash
ls -F Desktop/data-shell/
```

Output:

```bash
creatures/  data/  molecules/  north-pacific-gyre/  notes.txt  pizza.cfg  solar.pdf  writing/
```

</div>