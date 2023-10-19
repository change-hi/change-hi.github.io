---
title: "11. Configuring and Using Rclone"
published: true
morea_id: experience-configuring-rclone
morea_type: experience
morea_summary: "Understand how to configure and use Rclone."
morea_sort_order: 11
morea_labels:
  - 3:05pm
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

# 11. Using Rclone
---

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone21.png" alt="Node anatomy" caption="" %}

Rclone is a free utility for syncing directories between object storage systems (such as Amazon S3, Dropbox, Google Drive etc) and file based storage (e.g. home or scratch))

https://rclone.org

---
# Rclone in KOA

Rclone is installed on KOA and can be used in the command line via 
<div class="alert alert-secondary" role="alert" markdown="1">

```
$ rclone
```

</div>

# Configuring Rclone

Before you can use Rclone, you must configure it 
This configuration step will set up access for the remote object storage system that you want to transfer data to and from
In this tutorial we will configure Google Drive since UH has Google for Education and everyone at UH has it

# Open a Shell Session on KOA
1.) Start a shell session on KOA through your own terminal or you can use Open OnDemand via [https://koa.its.hawaii.edu/]
*You WILL be prompted for DUO two-factor verification.

2.) Navigate to Clusters -> _Koa_Shell_Access, to start your session

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_0.png" alt="koa access cluser" caption="" %}

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

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_1.png" alt="Node anatomy" caption="" %}

 You'll be prompted for the name of the remote object storage system\, we use "rclone\-gdrive" in this tutorial  

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone-gdrive
```

</div>

---

# Choosing a Storage Option

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_2.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ 18
```

</div>

* Choose #18, Google Drive as Storage Option
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
# Advanced Configuration

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ n
```

</div>

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_3.png" alt="Node anatomy" caption="" %}
---

---
# Auto Authenticate 

In this tutorial we are running RClone on a remote machine (KOA).

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ n
```

</div>

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_4.png" alt="Node anatomy" caption="" %}
---
 # Optional config_token

 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_5.png" alt="Node anatomy" caption="" %}

 # Access the config_token from your local RClone <br>
 1.) Confirm RClone is successfully installed on your machine by running `rclone version` in your CLI of choice. <br>
 2.) From the KOA shell copy/paste and run the `rclone authorize` command into your local CLI <br>

 <div class="alert alert-secondary" role="alert" markdown="1">
```
$  rclone authorize "drive" "<AUTH CODE>"
```

</div>

Example: Windows Powershell
 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_6_PS.png" alt="Node anatomy" caption="" %}

3.) A browser window should open, prompting you to sign into your Google Drive Account
{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_6_google.png" alt="Node anatomy" caption="" %}

4.) Allow RClone to access your Google Drive
{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_6_google_allow.png" alt="Node anatomy" caption="" %}

5.) Once you allow access, you will see a 'Success' screen:
{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_6_google_success.png" alt="Node anatomy" caption="" %}

6.) Navigate back to your CLI, to view the generated token, copy the token

Example: Windows Powershell
 {% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone_KOA_7_PS.png" alt="Node anatomy" caption="" %}

7.) Paste the token into KOA
 <div class="alert alert-secondary" role="alert" markdown="1">
```
$  config_token> <YOUR CONFIG TOKEN>
```

</div>



# Configuring of Google Drive

-Do not configure as a team drive

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RClone20.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ n
```

</div>

---

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/Rcloneconfig.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ y
```

</div>

---



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

{% include next-button.html
  top-label="Transfer RClone ->"
  bottom-label="3:25pm"
  url="/morea/data-movement/experience-transferring-rclone.html" %}