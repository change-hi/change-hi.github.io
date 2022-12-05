---
title: "Data Movement Workshop 2022 Assessment Results"
published: true
morea_id: data-movement-workshop-2022-assessment-results
morea_type: reading
morea_summary: "Participant comments, instructor comments, and discussion"
morea_sort_order: 0
morea_labels:
morea_enable_toc: false
---

# Data Movement Workshop 2022 Assessment Results

## Participant Assessment Comments

*What is a simple way to test the speed of the network connected to your laptop? If you don't recall, just write "I don't recall".*

* speedtest.net (3 responses)
* LibreSpeedTest (3 responses)
* Don't recall

*Why might you want to use the FileZilla client? If you don't recall, just write "I don't recall".* 

* easy to set up ftp transfer
* To have a GUI for transferring files
* Easy to use, interactive.
* visual file browsing, saved connections
* for faster data transfers
* A GUI based alternative to commands such as scp or rsync
* It is another way to upload and download files to and from a remote computer using sftp. It may be good to use if you aren't familiar with using sftp on the command line.

*Why might you want to use the Globus service? If you don't recall, just write "I don't recall".*

* file transfer between GridFTP servers
* To be able to share files from any device and within people on a team
* Unattended transfer; uses existing institutional login.
* resumable/interruptible
* For reliable data transfer
* For the transfer of large data across institutions
* Globus is an interface that allows you to move data from different sources you can connect to (your own laptop, desktop, HPC, etc.)

*Has this workshop material caused you to consider making changes to the way you move data in your own research and/or practice? If so, please briefly describe what changes you might make. If not, just write "No changes at the moment."*

* No changes at the moment (3x)
* I will use scp more in my research to move files more efficiently than uploading them one at a time using OOD
* Yes. It has made me consider using Globus for when I want to transfer some of the larger tarballs I have.
* Yes, Globus seems like a great tool to use for transferring data and I will consider it next time I need to transfer data to/from a remote computer. In the past I have just done sftp on the command line.

*In general, did you find the CONTENT of this workshop to be useful?  If so, please briefly summarize up to three skills you acquired (or started to acquire) as a result of this workshop.  If not, please write "Content not useful."*

* Content not useful
* Learned about new tools, practice using curl, practice using some of the tools
* I learned how to use scp, I learned about how to install globus, and learned how to use the --help option
* Yes, useful. like the summary of different transfer methods.
* Configuring globus, great review of network from alan
* Information regarding the different kinds of networks in use. Insight into how queues work and keywords that could be useful for future debugging. Learning about other data transfer tools besides rsync and scp that I might use in the future.
* The content is helpful and will be good to come back to. Globus is a tool I'd consider using and seems simple to use, the walkthrough nice. It has been a few months since I've used sftp on the command line so small exercises were a good refresher. It was interesting to learn about networks and how were are connected to different places.

*In general, did you find the PEDAGOGY (i.e. method of teaching) of this workshop to be appropriate?  If so, please briefly summarize one or two teaching methods you found to be useful. If not, please write "Pedagogy was not appropriate."*

* Pedagogy was not appropriate
* Yes, it was OK (2x)
* It was appropriate, I especially liked the exercises, I was able to follow along with the workshop
* Yes, interactive problems were great, along with the descriptions
* I found it to be appropriate where the first portion of the workshop was gave insight into the workings behind data transfer. The second portion had a quick hands on on using the tools.
* Yes, I liked how this workshop went over a few different ways to transfer data and had a few simple exercises along the way.

*No workshop is perfect. What are one or two things you would suggest we change to improve this workshop in future?  If you can't think of anything, then write "You're wrong. This workshop was perfect."*

* You're wrong. This workshop was perfect. (2x)
* Maybe a way to indicate when we were done with the exercise, I sometimes felt a bit rushed moving onto the next part of the workshop
* Make the slides and recording available to the participants. (I know, you're gonna do that.)
* I would have wanted to see more activities in this workshop. I did not understand the use of transferring data at higher speeds.
* Maybe more time towards using Globus, but considering the setup overhead to start using it, it was understandable why it was not dwelled upon. In other words, you're wrong. This workshop was perfect.
* I don't have the strongest computer science background, so some of the smaller details about networks were difficult to grasp.


*Did this workshop result in any new potential collaborations (i.e. people who you might contact in future to discuss research and/or professional issues)?*

* 4 responses: No the workshop did not result in any new potential collaborations
* 3 responses: I am not sure if the workshop resulted in any new potential collaborations

*If the workshops resulted in any new potential collaborations, are any of them with people outside your "home" discipline (i.e. your department)?*

* 4 responses: No.
* 2 responses: I don't know
* 1 response: Yes

*Do you have any ideas for new workshops that would help you with your research and professional development? If so, please briefly describe. If not, please write ("No ideas at the moment.")*

* Collaborate with students from other disciplines to solve problems together.

*Is there anything else you would like us to know about this workshop?*

* Thanks for offering this.
* just FYI i noticed the instructions for Rclone (with Google Drive) finally stopped working (as of Oct 3 2022) since google deprecated their OOB API credential verification.
  <https://change-hi.github.io/morea/data-movement/reading-configuring-rclone.html>
  Google's docs: <https://developers.google.com/identity/protocols/oauth2/resources/oob-migration>
* Awesome job presenting this workshop!

## Instructor Assessment Comments

*For your workshop, how would you rate the overall "success" of the workshop (i.e. your subjective sense of things like student engagement, questions, discussion, completion of activities, etc.)?*

* 1 response: About as successful as expected.


*What aspects of your workshop did not work as well as possible, and what are your thoughts on how to improve them in future?*

* The primary aspect of the workshop that didn't work as well as I had hoped was activities and engagement. I am not sure how to improve this in the future as, from my perspective, the workshop introduces a number of great tools but doesn't lend itself to viewer interactions very well.

*What aspects of your workshop do you feel worked well (so that we know to encourage their use in future workshops when appropriate)?*

* In terms of content, the workshop provides a plethora of great information that viewers can easily implement to better use the tools available to them.

*Is there anything else you would like us to know about your workshop? Are there ways we can better support your instruction in future?*

* Depending on the workshop, it is hard to relate the material to the fellows; however, the process felt as if I was just going through the motions and very disconnected to the overall material and value of the workshop.

## Discussion and recommendations

The initial questions assess several of the learning outcomes.  The responses provide evidence that the learning outcomes assessed were, in general, achieved.  

About half the respondants indicated they did not see an immediate application of this material to their own research.  On the other hand, about half said they *did* see an application to their own research. Maybe a 50% hit rate is totally fine? 

Recommendations for next time:

1. Perhaps try to trim some introductory material by 5-10 minutes and allocate that time to going deeper into Globus, since that is the most impactful aspect of the workshop.

2. An instructor brought up an interesting point: they did not know much about the background of the fellows, so it was more difficult to connect the material directly to them. This is something we could address more globally in future. For example, we could have the Data Fellows create a "profile" about their research interests, technical background, and self-identified "gaps" in knowledge at the beginning of the year. Then instructors of all workshops could review the profiles and tailor the contents and delivery more specifically to the participants. 

3. Update the RClone reading.
