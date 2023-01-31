---
title: "11. Transferring Data using Globus "
published: true
morea_id: experience-transferring-data
morea_type: experience
morea_summary: "Understand how to setup and use Globus to move data."
morea_sort_order: 9
morea_labels:
  - 3:40pm
morea_enable_toc: true
---

# 11. Transferring Data using Globus

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
 
 **Questions**
* How do I move data from my machine using Globus?
* How do I move data to my machine with Globus? 

**Objectives**
* Move sample data from a repository using Globus, then to your computer using Globus.  
</div>

## Transferring Data from and to Mana Using Globus Connect Personal

After you’ve signed up and logged in to Globus, you’ll begin at the File Manager.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone10.png" alt="Node anatomy" caption="" %}


The first time you use the File Manager, all fields will be blank.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone11.png" alt="Node anatomy" caption="" %}


<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Key Concept: Collection**
<hr/>

A collection is a named location containing data you can access with Globus. Collections can be hosted on many different kinds of systems, including campus storage, HPC clusters, laptops, Amazon S3 bucket, Google Drive (these are “premium” connectors so a seperate subscription is required), and scientific instruments.
</div>


When you use Globus, you don’t need to know a physical location or details about storage. You only need a collection name. A collection allows authorized Globus users to browse and transfer files. Collections can also be used for sharing data with others and for enabling discovery by other Globus users. [Globus Connect](https://www.globus.org/globus-connect) is used to host collections.

## Access a collection

Click in the Collection field at the top of the File Manager page and type ”UH-HPC". Globus will list collections with matching names. Choose UH-HPC.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone12.png" alt="Node anatomy" caption="" %}


Globus will connect to the UH-HPC collection and display the default directory, /~/.  This is your home directory in the Mana Globus endpoint. Click on “Transfer or Sync to”.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone13.png" alt="Node anatomy" caption="" %}


## Request a file transfer

A new collection panel will open, with a ”Search" field at the top of the panel. Click on it:

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone14.png" alt="Node anatomy" caption="" %}

Click on “Your Collection” tab. Find the Globus Connect Personal endpoint you created earlier and click on it.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone15.png" alt="Node anatomy" caption="" %}

On the left collection, UH-HPC, select the file you would like to transfer. The Start> button at the top of the panel will activate. Click the Start> button to transfer the selected files to the collection in the right panel.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone16.png" alt="Node anatomy" caption="" %}


Globus will display a green notification panel—confirming that the transfer request was submitted—and add a badge to the “Activity” item in the command menu on the left of the page. Click Activity in the command menu on the left of the page to go to the Activity page.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone17.png" alt="Node anatomy" caption="" %}

To confirm transfer completion, go to the Activity page and click the arrow icon on the right to view details about the transfer. You will also receive an email with the transfer details.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone18.png" alt="Node anatomy" caption="" %}


## Activity Page

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone19.png" alt="Node anatomy" caption="" %}

If you notice that the transferred files are not listed in the right panel with your Globus Connect Personal collection. Click the refresh icon (circular arrows) at the top of the collection panel to see the updated contents.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/globus_and_rclone20.png" alt="Node anatomy" caption="" %}

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Discussion**
<hr/>

Do you have any questions about Globus? Ask away!

</div>

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

* A collection is a named location containing data you can access with Globus.
* Collections can be hosted on many different kinds of systems.  
</div>



{% include next-button.html
  top-label="Assessment ->"
  bottom-label="3:50pm"
  url="/morea/data-movement/assessment-data-movement.html" %}
