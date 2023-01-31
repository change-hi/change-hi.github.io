---
title: "6. Transfer Programs"
published: true
morea_id: experience-transfer-programs
morea_type: experience
morea_summary: "Be able to identify common/best transfer applications."
morea_sort_order: 6
morea_labels:
  - 2:50pm
morea_enable_toc: true
---
# 6. (Our $0.02 about) Transfer Programs

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
 
 **Questions** 
  * What are some of the most common/best transfer applications? 

 **Objectives**
  * Introduce some of the basic data transfer applications used in research. 

</div>


## Scp, sftp, rsync, other SSH-based

* Very accessible
* Have a problem with long-haul
  * [https://www\.psc\.edu/hpn\-ssh\-home/hpn\-ssh\-faq/](https://www\.psc\.edu/hpn\-ssh\-home/hpn\-ssh\-faq/)
  * Can be patched to work much better, if you are invested in an ssh-based workflow
* Common tools in this category are single-threaded
  * Versus support for parallel transfers


## GridFTP (including Globus GridFTP)

 * Breaks files into small pieces, transfers many pieces concurrently, and reassembles them at the receiving end
 * Tends to get better performance out of networks with symptoms.
 * May not tend to get better performance out of transfer paths with other problems
 * Authentication and licensing might present obstacles to use in ad-hoc workflows

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone4.png" alt="Node anatomy" caption="" %}


## Lftp

* Very versatile (Russian origin) program with features such as mirroring and parallel transfers

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep60.png" alt="Node anatomy" caption="" %}

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>
 
  * SFTP, although common, is not the best application for moving data and there exists other SSH versions and tools that are better to transfer large data. 
</div>

{% include next-button.html
  top-label="Scientific Data Transfer Examples ->"
  bottom-label="3:00pm"
  url="/morea/data-movement/experience-data-transfer-examples.html" %}
