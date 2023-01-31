---
title: "10. Globus Installation "
published: true
morea_id: experience-globus-install
morea_type: experience
morea_summary: "Understand how to setup and use Globus to move data."
morea_sort_order: 9
morea_labels:
  - 3:35pm
morea_enable_toc: true
---

# 10. Globus Installation

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
 
 **Questions**
* How do I create a Globus account using my UH credentials?
* How do I install Globus Connect Personal on my PC, Mac, Linux, or Unix? 

**Objectives**
* Connect your UH account with Globus. 
* Install Globus on to your system.  
</div>

## Transfering Files with Globus

Visit www.globus.org and click "Login" at the top of the page. On the Globus login page, type in University of Hawaii. When you find it, click Continue.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone5.png" alt="Node anatomy" caption="" %}

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-triangle-exclamation fa-xl"></i> **Please Note**
<hr/>

* UH does not provide a Globus subscription for external collaborators 
* Default settings may not include data sharing
</div>


You’ll be redirected to your UH login page. Use your UH credentials to login:

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone6.png" alt="Node anatomy" caption="" %}

Some organizations will ask for your permission to release your account information to Globus. Once you’ve logged in with your UH credentials, Globus will ask if you’d like to link to an existing account. 

If this is your first time logging in to Globus, click "Continue." If you’ve already used another account with Globus, you can choose "Link to an existing account."

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone7.png" alt="Node anatomy" caption="" %}


> You may be prompted to provide additional information such as your organization and whether or not Globus will be used for commercial purposes. Click on non-profit research or educational purposes. Complete the form and click "Continue."


{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone8.png" alt="Node anatomy" caption="" %}


Finally, you need to give Globus permission to use your identity to access information and perform actions (like file transfers) on your behalf.


{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone9.png" alt="Node anatomy" caption="" %}


## Globus Connect Personal

Globus Connect Personal turns your laptop or other personal computer into a Globus endpoint with just a few clicks. With Globus Connect Personal you can share and transfer files to/from a local machine—campus server, desktop computer or laptop—even if it's behind a firewall and you don't have administrator privileges.

* Globus Connect Personal puts the power of Globus on your computer.

* Dramatically increases data transfer speeds over scp and other transfer tools.

* Automatically suspends transfers when computer sleeps and resumes when turned on.

* Installs in seconds using native operating system install packages.

* Works with firewalls that block incoming connections, and behind most NATs.

* Uses proven Globus infrastructure for security and authentication.

## Installation Instructions

_[Globus Connect Personal for Mac](https://docs.globus.org/how-to/globus-connect-personal-mac)_  __for Mac OS X 10\.7 or higher \(Intel only\)__

_[Globus Connect Personal for Linux](https://docs.globus.org/how-to/globus-connect-personal-linux)_  __for common x86\-based distributions__

_[Globus Connect Personal for Windows](https://docs.globus.org/how-to/globus-connect-personal-windows)_  __for recent Windows versions__

<div class="alert alert-warning" role="alert" markdown="1">
<i class="fa-solid fa-triangle-exclamation fa-xl"></i> **Note**
<hr/>

> Once you are done installing GCP, the Globus Connect Personal agent will be running in the background. 
> Once you disconnect from it, you can launch the application again by clicking “command + space bar” keys on Mac machine or Windows key on Windows machine and typing “globus” to select the application to restart it.
</div>

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

  * Dual factor authentication is a prerequisite to using Globus with MANA.
  * Both systems to transfer data to and from must have Globus installed on them. 
</div>

{% include next-button.html
  top-label="Transferring Data ->"
  bottom-label="3:40pm"
  url="/morea/data-movement/experience-transferring-data.html" %}
