---
title: "Setting Up Mana"
published: true
morea_id: reading-ssb-mana
morea_type: reading
morea_summary: "Create accounts on Mana, download sample file."
morea_sort_order: 1
morea_labels:
  - Pre-workshop setup (10 minutes)
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Objectives**
  * Have an account on Mana
  * Have UH Duo/MFA enabled
  * Be able to connect to the workshop in Zoom and Mana Open OnDemand via a web browser
  * Download sample data
</div>


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

## Your compute node is assigned

Start a shell:

{% include figure.html url="" max-width="100%" file="/morea/scientific-software-basics/fig/are_you_sure.png" alt="Node anatomy" caption="" %}

Answer yes:

Warning: Permanently added ‘gpu-0016.hpc.ci.its.hawaii.edu,10.100.11.214’ (ECDSA) to the list of known hosts. Authentication failed. Your connection to the remote server has been terminated.

Go back to "my interactive sessions" in the browser and start another shell..

## Download data-shell.zip:

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Download data-shell.zip**
<hr/>

First:

```bash
wget https://ci-tracs.github.io/Scientific_Software_Basics/data/data-shell.zip
```
Second:

```bash
unzip data-shell.zip
```
</div>
