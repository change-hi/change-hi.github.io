---
title: "Configure and Using Rclone"
published: true
morea_id: reading-configuring-rclone
morea_type: reading
morea_summary: "Understand how to configure and use Rclone."
morea_sort_order: 1
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

<img src="../assets/img/globus_rclone/globus_and_rclone21.png" width=600px />

Rclone is a free utility for syncing directories between object storage systems (such as Amazon S3, Dropbox, Google Drive etc) and file based storage (e.g. home or scratch))

https://rclone.org

---
# Rclone in MANA

Rclone is installed on the Mana Data Transfer Nodes and can be used in the command line via 

~~~
$ rclone
~~~
{: .language-bash}

# Configuring Rclone

Before you can use Rclone, you must configure it 
This configuration step will set up access for the remote object storage system that you want to transfer data to and from
In this tutorial we will configure Google Drive since UH has Google for Education and everyone at UH has it

# Open a Shell Session on MANA
1.) Start a shell session on MANA through your own terminal or you can use Open OnDemand via https://mana.its.hawaii.edu

Clusters -> >_Mana_Shell_Access

From your terminal/shell ssh to one of the Mana DTNs

~~~
$ ssh username@hpc-dtn1.its.hawaii.edu
~~~
{: .language-bash}

*You may be prompted for your password depending on where you are SSHing from and you WILL be prompted for DUO two-factor verification.

# Two Factor Authentication
Example 

~~~
$ ssh luketn@hpc-dtn1.its.hawaii.edu
~~~
{: .language-bash}

<img src="../fig/RClone1.png" width=600px />

---

Two Factor Authentication for Duo Push
~~~
$ 1
~~~
{: .language-bash}

Two Factor Authentication for Phone Call
~~~
$ 2
~~~
{: .language-bash}

Two Factor Authentication for SMS
~~~
$ 3
~~~
{: .language-bash}


<img src="../fig/Rclone2.png" width=600px />
---

# Configuring Rclone

~~~
$ rclone config
~~~
{: .language-bash}

<img src="../fig/RClone3.png" width=600px />

---

~~~
$ n
~~~
{: .language-bash}

<span style="color:#595959">No remotes found \- make a new one</span>

<span style="color:#595959">n\) New remote</span>

<span style="color:#595959">s\) Set configuration password</span>

<span style="color:#595959">q\) Quit config</span>

---

<span style="color:#000000">Choose a name for the remote object storage system</span>

<img src="../fig/RClone4.png" width=600px />

<span style="color:#595959">You'll be prompted for the name of the remote object storage system\, we use "rclone\-gdrive" in this tutorial</span>

~~~
$ rclone\-gdrive
~~~
{: .language-bash}

---

# Choosing a Storage Option

<img src="../fig/RClone6.png" width=600px />

~~~
$ 15
~~~
{: .language-bash}

- Choose #15, Google Drive as Storage Option
** See help for drive backend at: https://rclone\.org/drive/ **

---

# Google Application Client Id

<img src="../fig/RClone7.png" width=600px />

*Setting your own is recommended, see https://rclone\.org/drive/\#making\-your\-own\-client\-id for how to create your own.
- If you leave this blank, it will use an internal key which is low performance.
- I leave this blank in my tutorial

Client Secret
- I also leave this blank in my tutorial

OAuth Client Secret
- Leave blank normally.

Scope
- 1  Full access all files, excluding Application Data Folder.
    "drive"

- 2  Read-only access to file metadata and file contents.
    "drive.readonly"
    Access to files created by rclone only.
- 3 These are visible in the drive website.
    File authorization is revoked when the user deauthorizes the app.
    "drive.file"
    Allows read and write access to the Application Data folder.
- 4 This is not visible in the drive website.
    "drive.appfolder"
    Allows read-only access to file metadata but
- 5 does not allow any access to read or download file content.
    "drive.metadata.readonly"
<img src="../fig/RClone8.png" width=600px />

~~~
$ 1
~~~
{: .language-bash}

<img src="../fig/RClone9.png" width=600px />

---

Leave ID of the root folder blank normally

<img src="../fig/RClone10.png" width=600px />

---
# Auto Configuration

~~~
$ n
~~~
{: .language-bash}

<img src="../fig/RClone13.png" width=600px />

---

You should receive a verifiable link after configuration is complete

<img src="../fig/RClone14.png" width=600px />

---

# Google Validation

<img src="../fig/RClone16.png" width=400px />

---
# Copy Validation Code and Enter in MANA

<img src="../fig/RClone21.png" width=400px />

---
# Configuring of Google Drive

<img src="../fig/Rcloneconfig.png" width=400px />

~~~
$ y
~~~
{: .language-bash}

---

-Do not configure as a team drive

<img src="../fig/RClone20.png" width=600px />

~~~
$ n
~~~
{: .language-bash}

- Quit Configuration

~~~
$ q
~~~
{: .language-bash}

---

# Now we can list files from GDrive

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

  * Rclone must be configured on a server for your user before it can be used to transfer data.
</div>
