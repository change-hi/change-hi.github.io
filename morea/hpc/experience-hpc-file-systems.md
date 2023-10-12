---
title: "7. Staging and File System Choice"
published: true
morea_id: experience-hpc-file-systems
morea_type: experience
morea_summary: "What is a file system? What is a distributed file system? How do you optimize the file system on Koa?"
morea_sort_order: 7
morea_labels:
  - 3:40pm-3:50pm
morea_enable_toc: true
---

# 7. Staging and File System Choice

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
  * What is a file system?
  * What is a distributed file system?
  * How do you optimize the file system on Koa?

**Objectives**
  * Understand general file system and distributed file system concepts. Understand the general HPC System architecture.
  * Be able to stage files on Koa scratch.
</div>


## What is a file system?

The term file system is ubiquitous among operating systems. At some point in time, you may have had to format a USB flash drive (SD card, memory stick) and may have to choose between different file systems such as FAT32 or NTFS (on a Windows OS), exFat or Mac OS Extended (on a Mac).

{% include figure.html url="" max-width="100%" file="/morea/hpc/fig/inode.png" alt="Inode" caption="Inode Table (https://www.bluematador.com/blog/what-is-an-inode-and-what-are-they-used-for) "%}

File systems are ways in which operating systems organize data (i.e. documents, movies, music) on storage devices. From the storage device hardware perspective, data is represented as a sequence of blocks of bytes, however that by itself isn’t useful to regular users. Regular users mostly care about file and directory level abstraction and rarely work with blocks of bytes! Luckily, the file system under the hood handles the organization and locating logic of these blocks of bytes for the users so that you can run your favorite commands (e.g., ls) and applications. For example in a Linux file system, “file” information is stored in an inode table (illustrated in figure above) as sort of a lookup table for locating corresponding blocks of a particular file on disk. Located blocks are combined together to form a single file which the end user can work with.

## What is a distributed file system?

On a cluster, blocks of data that make up a single file are distributed among network attached storage or NAS devices. Similar principles apply here, the goal of a cluster file system is still to organize and locate blocks of data (but across network!) and present them to the end user as one contiguous file. One main benefit of stringing storage devices together into a network connected cluster is to increase storage capacity beyond what a single computer can have. Imagine working with 100 TB files on your laptop. Of course, the storage can be shared with different cluster users further increasing utilization of these storage devices.

Koa users have a special foldera called koa_scratch where they can temporarily store data on the cluster. Note that the scratch folders will be purged after some period of time, please save your important files into your home directory.

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Locate Lustre File System Scratch On Koa**
<hr/>

Let's locate our scratch folder.

First create a new cell in our Jupyter Lab Notebook after the first cell.

Paste the code into the cell and run. 

The pwd command will print where you are in the directory tree and it should be something like "/home/username".

The ls command will print files and directory that are available in your home/username directory. You should see "koa_scratch" listed in the print out.

Note that the '!' symbol below allows us to execute terminal commands in our Jupyter Lab Notebook cell.

```python
!pwd
!ls
```
</div>

### The Lustre File System.

{% include figure.html url="" max-width="60%" file="/morea/hpc/fig/lustre.png" alt="Lustre File System" caption="Lustre File System (https://wiki.lustre.org/Introduction_to_Lustre)" %}

Lustre is a parallel distributed file system, where file operations are distributed across multiple file system servers. In Lustre, storage is divided among multiple servers allowing for ease of scalability and fault tolerance. This file system is great for high speed read/write performance.

### The NFS File System

{% include figure.html url="" max-width="40%" file="/morea/hpc/fig/nfs.png" alt="NFS File System" caption="NFS File System (https://www.geeksforgeeks.org/what-is-dfsdistributed-file-system/)" %}

NFS is a single server distributed file system where file operations are not parallel across servers but a single server serves requests to the cluster. NFS is an older technology and has the advantage of having gone through the test of time and is trusted among cluster architects.

## Choosing the right file system for performance

Depending on the user's need, different file systems are optimized for different purposes. One may be optimized for random access speed, one with error correcting capability, or one with high redundancy to prevent loss of data. 

On Koa we have 2 locations for file storage: "home/user" and "koa_scratch" folders available to us.

On Koa, our "home/user" directory resides on an NFS file system server. Though "home/user" is great for storing our files on the cluster, it's serverly lacking in read/write performance. 

For the best performance (read/write speed) we will mostly want to use "koa_scratch". As discussed above, the reason is because Lustre file system distributes workload accross multiple meta servers, while NFS is a single server file system. In addition, Koa lustre file system is configured with solid state drives while NFS file system is configured with hard drives, improving Koa lustre file system read/write speed further.

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Solid State Drive vs. Hard Drive Performance**
<hr/>

Solid state drives can read up to 10 times faster and writes up to 20 times faster than hard disk drives.

You can read more about it [here](https://www.avg.com/en/signal/ssd-hdd-which-is-best#:~:text=A%20solid%20state%20drive%20reads,PCIe%203.0%20to%204.0%20connectors).
</div>

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: List Disk Usage Information**
<hr/>

On Koa, there's a command that lists disk usage on the cluster.

Create a new cell below our previous block.

Paste the code into the cell and run.

You should see a table that lists disk space used and remaining space.

```python
!usage
```
You can also see your personal disk usage upon logging into the cluster. 

{% include figure.html url="" max-width="100%" file="/morea/hpc/fig/koa_storage.png" alt="View storage use on cluster." caption="" %}
</div>

<div class="alert alert-success" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

* File system is a way in which operating systems organize data on storage devices.
* Distributed file system organizes data accross network attached storage devices.
* Distributed file system has the advantage of supporting larger scale storage capacity.
* Koa supports lustre and NFS file systems.
* Lustre on Koa is setup with solid state drives.
* NFS on Koa is setup with spinning (hard disk) drives.
</div>

{% include next-button.html 
           top-label="Assessment ->" 
           bottom-label="3:50pm" 
           url="/morea/hpc/assessment-hpc-workshop.html" %}
