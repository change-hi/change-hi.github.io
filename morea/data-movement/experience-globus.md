---
title: "9. Globus"
published: true
morea_id: experience-globus
morea_type: experience
morea_summary: "Understand what Globus is."
morea_sort_order: 9
morea_labels:
  - 3:30pm
morea_enable_toc: true
---
# 9. Globus

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* What does Globus do and how can I use it with my data? 
 
**Objectives**
* Have a basic understanding of Globus and how to move data. 

</div>
{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone4.png" alt="Node anatomy" caption="" %}

## Purpose of Globus 

Globus can use several different systems to move data
* Laptop? 
* HPC cluster? 
* Cloud storage? 
* Tape archive? 
Access them all using just a web browser.

Data stored at a different institution? At a supercomputing facility? All you need is your campus login.

Globus is a service that makes it easy to move, sync, and share large amounts of data.

Globus will manage file transfers, monitor performance, retry failures, recover from faults automatically when possible, and report the status of your data transfer.

Data transfer limitations of google drive

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone2.jpg" alt="Node anatomy" caption="" %}


## Background

* Globus uses GridFTP for more reliable and high-performance file transfer, and will queue file transfers to be performed asynchronously in the background.
* Globus was developed and is maintained at the University of Chicago and is used extensively at supercomputer centers and major research facilities. 
* [https://globus.org](https://globus.org)

## When To use Globus

* To transfer or share data between two Globus managed endpoints (e.g. two multi-user systems at different universities, each running a Globus server)
* To transfer data between a managed endpoint (e.g. UH-HPC) to a Globus Connect Personal endpoint (e.g. your desktop)

## Globus Plus

For certain types of data transfer or sharing, you will need Globus Plus, the UH Globus subscription includes Globus Plus services, but you need to request a globus plus invite.

These scenarious include:
*   To share data from your Globus Connect Personal endpoint (eg. sharing data from your desktop)
*   Data transfer between 2 Globus Connect Personal endpoints (eg. sharing data between your desktop and laptop)
*   To transfer data from a Globus Connect Personal endpoint

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

* Globus is useful for transfering data to and from MANA at UH. 
</div>

{% include next-button.html
  top-label="Creating Globus Account and Globus Connect Personal Installation ->"
  bottom-label="3:35pm"
  url="/morea/data-movement/experience-globus-install.html" %}
