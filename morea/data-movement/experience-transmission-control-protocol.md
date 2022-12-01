---
title: "5. Transmission Control Protocol (TCP)"
published: true
morea_id: experience-transmission-control-protocol
morea_type: experience
morea_summary: "Understand what transmission control protocol is."
morea_sort_order: 5
morea_labels:
  - 2:40pm
morea_enable_toc: true
---

# 5. Transmission Control Protocol (TCP)

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
 
 **Questions** 
  * What is TCP? 
  
 **Objectives**
  * Obtain a basic understanding of TCP. 

</div>

## Why TCP Acts As It Does

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep51.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep52.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep53.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep54.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep56.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep57.png" alt="Node anatomy" caption="" %}

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>

Bandwidth throttling on MacOS:

<https://blog.leiy.me/post/bw-throttling-on-mac/>
</div>



## TCP Tuning

Bandwidth Delay Product (BDP)
   * TCP receive window = round_trip_time * effective_bit_rate
     * "Effective bit rate" is usually the smallest link in a path
     * Round Trip Time is propagation delay, queuing delay, backlog delay
   * TCP RWIN max is 2 Gigabytes
   * The max RTT that can support 100 Gbit/sec is 171.8 milliseconds
     * Meaning: in order to go further, you'd need more than max window
   * Most modern OS auto-tune, but have limits to the auto that can be raised.
   * Most default limits are insufficient for moving data fast over long distances

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>

The Fasterdata Knowledge Base provides proven, operationally sound methods for troubleshooting and solving performance issues.

<https://fasterdata.es.net/>
</div>



## Examples of packet pacing

### 4 streams, into a 12 Gbps disk system

#### No FQ pacing, 640 GB in 577 seconds

With no pacing, the 100 Gbps Ethernet interface sends packets in short bursts of 100 Gbps. 
Since our target rate is only 12 Gbps, we could distribute the packets more evenly, 
and possibly avoid having bursts arrive at one or more queues along the path to the receiver.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep58.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep59.png" alt="Node anatomy" caption="" %}


#### 3Gb per stream FQ pacing, 640 GB in 487 seconds

Notice that when we pace packets at the sender to spread them out, the transfer is much smoother, and there are no more 
TCP retransmissions

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep510.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep511.png" alt="Node anatomy" caption="" %}


## Other ways to tune

Ethernet driver ring buffers
   * The first and last queues in your network path

Ethernet Offloading
   * The Ethernet card does such things as TCP segmentation and checksums, relieving the computer operating system of those tasks

Ethernet flow control -- sometimes mitigates buffer issues

Storage system (formerly "disks") configuration
   * Multi-devices under a single volume (RAID-1 or mdadm)
   * high performance files systems
   * If you have a fast, clean 100G network, the next limit will be your storage throughput
   * [https://fasterdata.es.net/science-dmz/DTN/hardware-selection/storage/](https://fasterdata.es.net/science-dmz/DTN/hardware-selection/storage/)

MTU (IP maximum transmission unit) akin to Ethernet frame size

## Sometimes Less Is More

If you experience sickly performance due to queue loss
  * You might try reducing the max TCP receive window, if you can't affect queue pacing
  * Congested paths might get more done whenpresentedwith a lower rate that doesn't cause queue drops
  * This is a temporary, stop-gap suggestion

## Parallelism

Currently, up to 10 Gigabit Ethernet can be filled by a typical server grade computer

On 100 Gigabit, various transfer speeds > 80 Gbps have been recorded (see pic)

Working 100G flows tend to be 30 Gbps or less

Most transfers over 10 Gbps is using multiple connections

Globus GridFTP opens on the order of several hundred connections at once.


<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

  * Tuning TCP can have a large impact on transfer throughput. 
</div>

{% include next-button.html
  top-label="Transfer Programs ->"
  bottom-label="2:50pm"
  url="/morea/data-movement/experience-transfer-programs.html" %}
