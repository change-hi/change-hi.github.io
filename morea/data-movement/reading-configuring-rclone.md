---
title: "Configuring and Using Rclone"
published: true
morea_id: reading-configuring-rclone
morea_type: reading
morea_summary: "Understand how to configure and use Rclone."
morea_sort_order: 2
morea_labels:
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How do I configure Rclone?

 **Objectives**
  * Make Rclone ready for data transfer with gdrive. 

</div>

# Using Rclone
---

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone21.png" alt="Node anatomy" caption="" %}

Rclone is a free utility for syncing directories between object storage systems (such as Amazon S3, Dropbox, Google Drive etc) and file based storage (e.g. home or scratch))

https://rclone.org

---
# Rclone in MANA

Rclone is installed on the Mana Data Transfer Nodes and can be used in the command line via 
<div class="alert alert-secondary" role="alert" markdown="1">

```
$ rclone
```

</div>

# Configuring Rclone

Before you can use Rclone, you must configure it 
This configuration step will set up access for the remote object storage system that you want to transfer data to and from
In this tutorial we will configure Google Drive since UH has Google for Education and everyone at UH has it

# Open a Shell Session on MANA
1.) Start a shell session on MANA through your own terminal or you can use Open OnDemand via https://mana.its.hawaii.edu

Clusters -> >_Mana_Shell_Access

From your terminal/shell ssh to one of the Mana DTNs
<div class="alert alert-secondary" role="alert" markdown="1">
```
$ ssh username@hpc-dtn1.its.hawaii.edu
```

</div>
*You may be prompted for your password depending on where you are SSHing from and you WILL be prompted for DUO two-factor verification.

# Two Factor Authentication
Example 

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ ssh luketn@hpc-dtn1.its.hawaii.edu
```

</div>

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone1.png" alt="Node anatomy" caption="" %}

---

Two Factor Authentication for Duo Push

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ 1
```

</div>

Two Factor Authentication for Phone Call
<div class="alert alert-secondary" role="alert" markdown="1">
```
$ 2
```

</div>

Two Factor Authentication for SMS

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ 3
```

</div>


{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/Rclone2.png" alt="Node anatomy" caption="" %}
---

# Configuring Rclone

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone config
```

</div>


{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone3.png" alt="Node anatomy" caption="" %}

---
<div class="alert alert-secondary" role="alert" markdown="1">
```
$ n
```

</div>

No remotes found \- make a new one  

 n\) New remote  

 s\) Set configuration password  

 q\) Quit config  

---

Choose a name for the remote object storage system  

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone4.png" alt="Node anatomy" caption="" %}

 You'll be prompted for the name of the remote object storage system\, we use "rclone\-gdrive" in this tutorial  

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone\-gdrive
```

</div>

---

# Choosing a Storage Option

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone6.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ 15
```

</div>

* Choose #15, Google Drive as Storage Option
** See help for drive backend at: https://rclone\.org/drive/ **

---

# Google Application Client Id

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone7.png" alt="Node anatomy" caption="" %}

*Setting your own is recommended, see https://rclone\.org/drive/\#making\-your\-own\-client\-id for how to create your own.
* If you leave this blank, it will use an internal key which is low performance.
* I leave this blank in my tutorial

Client Secret
* I also leave this blank in my tutorial

OAuth Client Secret
* Leave blank normally.

Scope
* 1  Full access all files, excluding Application Data Folder.
    "drive"

* 2  Read-only access to file metadata and file contents.
    "drive.readonly"
    Access to files created by rclone only.
* 3 These are visible in the drive website.
    File authorization is revoked when the user deauthorizes the app.
    "drive.file"
    Allows read and write access to the Application Data folder.
* 4 This is not visible in the drive website.
    "drive.appfolder"
    Allows read-only access to file metadata but
* 5 does not allow any access to read or download file content.
    "drive.metadata.readonly"

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone8.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ 1
```

</div>

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone9.png" alt="Node anatomy" caption="" %}

---

Leave ID of the root folder blank normally


{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone10.png" alt="Node anatomy" caption="" %}

---
# Auto Configuration

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ n
```

</div>

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone13.png" alt="Node anatomy" caption="" %}
---

You should receive a verifiable link after configuration is complete

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone14.png" alt="Node anatomy" caption="" %}

---

# Google Validation

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone16.png" alt="Node anatomy" caption="" %}

---
# Copy Validation Code and Enter in MANA

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone21.png" alt="Node anatomy" caption="" %}

---
# Configuring of Google Drive

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/Rcloneconfig.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ y
```

</div>

---

-Do not configure as a team drive

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone20.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ n
```

</div>

- Quit Configuration

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ q
```

</div>

---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

  * Rclone must be configured on a server for your user before it can be used to transfer data.
</div>
