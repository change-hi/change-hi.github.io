---
title: "2. Connecting to a remote HPC System"
published: true
morea_id: experience-hpc-connecting
morea_type: experience
morea_summary: "Understand how to connect to an HPC system and the basics of Open OnDemand"
morea_sort_order: 3
morea_labels:
  - 10 min (Teaching)
  - 10 min (Exercises)
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How do I log in to a remote HPC system?
* What is Open OnDemand and how do I use it?

**Objectives**
* Understand how to connect to an HPC system.
* Understand basics of Open OnDemand.
</div>

## Connecting to a Remote HPC system

The first step in using a cluster is to establish a connection from our laptop
to the cluster. When we are sitting at a computer (or standing, or holding it
in our hands or on our wrists), we have come to expect a visual display with
icons, widgets, and perhaps some windows or applications: a graphical user
interface, or GUI. Since HPC systems are remote resources that we connect
to over often slow or laggy interfaces (WiFi and Virtual private networks (VPN)s especially), it is more
practical to use a command-line interface, or CLI, in which commands and
results are transmitted via text, only. Anything other than text (images, for
example) must be written to disk and opened with a separate program.

If you have ever opened the Windows Command Prompt or macOS Terminal, you have
seen a CLI. If you have already taken a Carpentries' course on the UNIX
Shell or Version Control, you have used the CLI.
The only leap to be made here is to open a CLI on a *remote*
machine, while taking some precautions so that other folks on the network can't
see (or change) the commands you're running or the results the remote machine
sends back. These days, we use the Secure SHell protocol (or SSH) to open an encrypted
network connection between two machines, allowing you to send & receive text
and data without having to worry about prying eyes.

{% include figure.html url="" max-width="50%" file="/morea/hpc/fig/connect-to-remote.svg" alt="Connect to cluster" caption="" %}


## Traditional HPC system access using Secure Shell (SSH)

Most modern computers have a built in SSH client to their terminal.
Alternative clients exist, primarily for windows or add-ons to web browsers,
but they all operate in a similar manner. SSH clients are usually command-line tools, where you
provide the remote machine address as the only required argument.
If your username on the remote system differs from what
you use locally, you must provide that as well. If your SSH client has a
graphical front-end, such as PuTTY, MobaXterm, you will set these arguments
before clicking "connect." From the terminal, you'll write something like `ssh
userName@hostname`, where the "@" symbol is used to separate the two parts of a
single argument.

### Activity: Learn how to login using SSH
<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i> **Login to Mana**
<hr/>

```shell
ssh dav@mana.its.hawaii.edu
```

You may be asked for your password. **Watch out**: the
characters you type after the password prompt are not displayed on the screen.
Normal output will resume once you press `Enter`.

</div>



## Open OnDemand - An alternative to SSH

While, SSH is a common method to connect to remote systems (HPC or even servers), tools that provide
the same functionality and more exist.  One such tool is Open OnDemand (OOD).

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Learn more about Open OnDemand**
<hr/>

Created by Ohio Supercomputer Center, U. of Buffalo CCR, and Virginia Tech
and development funded by National Science Foundation under
grant numbers 1534949 and 1835725. [Learn more about Open OnDemand](http://openondemand.org/)
</div>


### Features of Open OnDemand

Open OnDemand works with a web browser making it possible to connect to an HPC system
with almost any device.  It has built in functionality for file browsing, uploading and downloading
smaller files, text editing, SSH terminal, and submitting interactive applications such as a remote desktop
on a compute node, Jupyter Lab and Rstudio.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Interactive applications at other institutions**
<hr/>

Various other interactive applications have been made for Open OnDemand but are not available by default.
See [here](https://osc.github.io/ood-documentation/master/install-ihpc-apps.html#) for a list of known interact applications.
</div>

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Browser choice and using an incognito or private browsing window**
<hr/>

While almost any modern browser should work with Open OnDemand, the developers recommend google chrome as it has the widest support
for the tools used to create Open OnDemand. [browser requirements](https://osc.github.io/ood-documentation/latest/requirements.html#browser-requirements)

For security it is recommend you use a private browsing window with Open OnDemand as this allows you completely
log out by just simplying closing the browser window.  While logout does exist in Open OnDemand, it may not work as
expected and really keep you logged in even after hitting logout.
</div>

### Activity: Learn how to login using Open OnDemand

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Login to Mana**
<hr/>

Open up your web browser and start a private browsing window.  Now, connect to the instance of Open OnDemand used with Mana by pointing your browser at [https://mana.its.hawaii.edu](https://mana.its.hawaii.edu).

{% include figure.html url="" max-width="75%"
file="/morea/hpc/fig/ood_landing.png"
alt="Connect to cluster" caption="" %}

</div>


### Feature: File browsing and editing

The file browser allows you to perform directory manipulation, create new files, upload and download files without having to know the command line.
The file browser can even has the ability to do text editing on files
which is useful if you are not familiar with a command line text editor.

### Feature: Command line text editors

Common text editors you find on HPC systems or linx systems include:
  * [Vi/Vim](https://www.vim.org/)
  * [Emacs](https://www.gnu.org/software/emacs/)
  * [nano](https://www.nano-editor.org/)

Of the three, nano is the simplest to use.

{% include figure.html url="" max-width="75%"
file="/morea/hpc/fig/ood_file_edit.png"
alt="Connect to cluster" caption="" %}

### Feature: Terminal in the browser

As Open OnDemand doesn't really replace the traditional commandline/SSH access method to HPC systems,
and instead makes the use of certain applications simpler, it still provides a way to bring up a commandline
on an HPC system within your web browser. 

{% include figure.html url="" max-width="80%"
file="/morea/hpc/fig/ood_shell_merged.png"
alt="Connect to cluster" caption="" %}

### Feature: Interactive applications

While Open OnDemand can allow you to access HPC systems using the terminal, it also has the ability to expand the ways
and HPC can be easily used though allowing the use of interactive applications that many have come to depend on.
{% include figure.html url="" max-width="75%"
file="/morea/hpc/fig/ood_interact.png"
alt="Connect to cluster" caption="" %}

### Feature: Email notification when jobs start

Each application has a form which you use to define the resources your job requires so that Open OnDemand can submit it on your behalf.
It also has the ability to email you once your job starts as not all jobs will begin immediately.
{% include figure.html url="" max-width="50%"
file="/morea/hpc/fig/ood_form.png"
alt="Connect to cluster" caption="" %}

Finally, when a job begins, it presents you with a button you can click to start up your interactive application and use it within your browser.

{% include figure.html url="" max-width="100%"
file="/morea/hpc/fig/ood_job.png"
alt="Connect to cluster" caption="" %}

## Key Points

<div class="alert alert-success" role="alert" markdown="1">

* SSH is the traditional method of connecting to HPC systems.
* Alternative tools like Open OnDemand exist to enhance the utility of and simplify the access to an HPC system
</div>

## Acknowledgements

Material used and modified from the [Introduction to High-Performance Computing Incubator workshop](https://carpentries-incubator.github.io/hpc-intro/).


<hr/>
For comparison purposes, here's the [Software Carpentry version of this page](https://ci-tracs.github.io/High_Performance_Computing/10-hpc/index.html)
