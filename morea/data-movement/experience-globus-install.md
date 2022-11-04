---
title: "10. Installing & Using Globus "
published: true
morea_id: experience-globus_install
morea_type: experience
morea_summary: "Understand how to setup and use Globus to move data."
morea_sort_order: 9
morea_labels:
  - 3:30pm
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
 
 **Objectives**
  * Connect your UH account with Globus. 
  * Install Globus on to your system.  

**Key Points**
  * Dual factor authentication is a prerequisite to using Globus with MANA.
  * Both systems to transfer data to and from must have Globus installed on them. 
</div>

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone4.png" alt="Node anatomy" caption="" %}


# Purpose of Globus 

Globus can use several different systems to move data
* Laptop? 
* HPC cluster? 
* Cloud storage? 
* Tape archive? 
Access them all using just a web browser.

> Data stored at a different institution? At a supercomputing facility? All you need is your campus login'

> Globus is a service that makes it easy to move, sync, and share large amounts of data.

> Globus will manage file transfers, monitor performance, retry failures, recover from faults automatically when possible, and report the status of your data transfer.

> Data transfer limitations of google drive

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone2.png" alt="Node anatomy" caption="" %}

# Background

* Globus uses GridFTP for more reliable and high-performance file transfer, and will queue file transfers to be performed asynchronously in the background.
*  Globus was developed and is maintained at the University of Chicago and is used extensively at supercomputer centers and major research facilities. https://globus.org

# When To use Globus

* To transfer or share data between two Globus managed endpoints \(e\.g\. two multi\-user systems at different universities\, each running a Globus server\)
* To transfer data between a managed endpoint \(e\.g\. UH\-HPC\) to a Globus Connect Personal endpoint \(e\.g\. your desktop\)

> ## Globus Plus
>
For certain types of data transfer or sharing, you will need Globus Plus, the UH Globus subscription includes Globus Plus services, but you need to request a globus plus invite
>These scenarious include:
> 1.)   to share data from your Globus Connect Personal endpoint (eg. sharing data from your desktop)
> 2.)   data transfer between 2 Globus Connect Personal endpoints (eg. sharing data between your desktop and laptop)
> 3.)   to transfer data from a Globus Connect Personal endpoint

{% include next-button.html
  top-label="Configure Rclone ->"
  bottom-label="3:40pm"
  url="/morea/data-movement/experience-rclone.html" %}