---
title: "Transferring Files with Rclone"
published: true
morea_id: reading-transferring-rclone
morea_type: reading
morea_summary: "Understand how to transfer files using Rclone."
morea_sort_order: 3
morea_labels:
morea_enable_toc: true
---

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
* How do I move data from google drive to MANA? 
* How do I move data from MANA to google drive?

 **Objectives**
  * Move data to and from MANA and gdrive. 

</div>

# Now we can list files from GDrive
* ‘lsf’ is how we list files using Rclone

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone lsf rclone-gdrive:/
```

</div>

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/Rclonesuccess.png" alt="Node anatomy" caption="" %}
---

# Now we can create a directory to transfer files to/from MANA/GDrive
* Make a directory called “rclonefiles” using the “mkdir” command

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ mkdir rclonefiles
```

</div>

* Move into the directory we just created

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ cd rclonefiles
```

</div>

* ‘cd’ is the change directory command

---

# Create a test document for transfer

In google drive create a folder name it “rclonetest” 

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RCloneGD1.png" alt="Node anatomy" caption="" %}

Within that folder create a new doc and call it “testfile”


{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/RCloneGD2.png" alt="Node anatomy" caption="" %}
---

# Copying the directory contents from GDrive to Mana

‘rclone copy’ has a source and destination required

GDrive being the source in the example below and the current directory (represented by the ‘.’) the destination

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone copy rclone-gdrive:/rclonetest .
```

</div>

This will copy the folder contents to the current directory - Note the ‘.’ at the end this is represents the current directory as the destination folder - we could also have used ~/rclonefiles or /home/username/rclonefiles as that same folder path.

---

# MANA to GDrive

* Create a testfile2.docx on the Mana DTN by copying testfile.docx

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ cp testfile.docx testfile2.docx
```

</div>


{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/Rclonecp.png" alt="Node anatomy" caption="" %}

‘cp’ is the copy command in the terminal/shell

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ ls
```

</div>

---

# Now copy testfile2.docx to GDrive 
The source is the Mana testfile2.docx and the destination is gdrive

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone copy testfile2.docx rclone-gdrive:/rclonetest
```

</div>

---

You can check GDrive and the file should appear!
{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/rclonetf.png" alt="Node anatomy" caption="" %}
---

The copy command on a folder will overwrite files that have the same name but if a files exists on the destination that isn’t in the folder being copied it will be retained on the destination (when we get to sync you will see a difference in this behavior)

The sync command is useful to keep a folder on GDrive and somewhere else with identical contents - meaning that if the destination folder has files that do not exist on the source they will be removed (so be careful)

---

# Rclone sync source destination

Let's remove testfile.docx and sync our rclonefiles folder to our GDrive rclonetest folder
<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rm testfile.docx
```

</div>

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ rclone sync ~/rclonefiles rclone-gdrive:/rclonetest
```

</div>

We should see in GDrive that now only testfile2.docx is there because the folders are in sync - Mana’s rclonefiles folder was the source so the GDrive rclonetest folder is now identical to rclonefiles

RClone large transfer - use nohup

For transfers that make take a long time that you do not wish to observe or that your connection might disconnect you should use ‘nohup’ so they run in the background until complete. Example of nohup ‘rclone copy’ below:

<div class="alert alert-secondary" role="alert" markdown="1">
```
$ nohup rclone copy source destination > nohup.out &
```

</div>

The ‘>’ after the destination will direct any standard output to be written to the nohup.out file and the ‘&’ on the end tells the shell to disconnect the command issued and run it in the background so you can still use your terminal/shell for other commands or exiting the session - the command issued with ‘nohup’ will continue to run.

---

# Rclone documentation

More information about Rclone and Google Drive can be found here:

[https://rclone.org/drive/#limitations](https://rclone.org/drive/#limitations)

You can download for your machine here [https://rclone.org/downloads/](https://rclone.org/downloads/)

Note - there is an experimental GUI for your laptop/workstation [https://rclone.org/gui/](https://rclone.org/gui/)

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

  * 'lsf' is how to list file with Rclone
  * rclone copy is used to copy files
  * rclone sync can be used to sync files across two storage systems
  * nohup can be used for large rclone file transfers to ensure your ssh session will not disconnect a transfer

</div>