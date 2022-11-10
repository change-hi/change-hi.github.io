---
title: "Setting Up Mana"
published: true
morea_id: reading-ssb-mana
morea_type: reading
morea_summary: "Create accounts on Mana, download sample file."
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

# Setting Up Mana

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Objectives**
  * Have an OOD compatible browser
  * Be able to connect to the workshop in Zoom and Mana Open OnDemand via a web browser
  * Download sample data
</div>

## Ensure you are using a compatible browser

Please make sure you have installed a compatible browser as specified at: <https://osc.github.io/ood-documentation/latest/requirements.html#browser-requirements>

## Connect to Mana through Open OnDemand

Connect to Mana by pointing your browser (ChromeOS, Firefox or Safari) at: <https://mana.its.hawaii.edu>

You should get the UH gold screen and then login with your user name and password.

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/gold_screen_crop.png" alt="Node anatomy" caption="" %}

Authenticate with MFA/DUO via your preferred method.

You should see the Mana Open OnDemand start page:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/mana_ood.png" alt="Node anatomy" caption="" %}

## Launch an interactive session on a compute node

Start an interactive session:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/select_desktop.png" alt="Node anatomy" caption="" %}

Your input values should be:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/check_ignition.png" alt="Node anatomy" caption="" %}

The output should look like this:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/waiting_for_a_session.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/my_interactive_session.png" alt="Node anatomy" caption="" %}

Click here:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/host_button.png" alt="Node anatomy" caption="" %}

## Assign a compute node

Start a shell:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/are_you_sure.png" alt="Node anatomy" caption="" %}

Answer yes:

Warning: Permanently added ‘gpu-0016.hpc.ci.its.hawaii.edu,10.100.11.214’ (ECDSA) to the list of known hosts. Authentication failed. Your connection to the remote server has been terminated.

Go back to "my interactive sessions" in the browser and start another shell..

## Download sample files for this workshop

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Download data-shell.zip**
<hr/>

1. Right click on [data-shell.zip](/morea/scientific-software-basics/data/data-shell.zip) and select "Save as..." to download this zip file to your computer.

2. Bring up a Terminal window (MacOS) or Command shell (Windows), find the data-shell.zip file, and run `unzip data-shell.zip` to create a folder called `data-shell` with several files and directories in it that will be used in this workshop. In MacOS (at least), you can just double-click the data-shell.zip file within the Finder to invoke the unzip command on it.  
</div>
