---
title: "3. Data Transfer Evaluation of the Network"
published: true
morea_id: experience-data-transfer-eval
morea_type: experience
morea_summary: "Understand what tools we use to test network throughput."
morea_sort_order: 3
morea_labels:
  - 2:20pm
morea_enable_toc: true
---
# 3. Data Transfer Evaluation of the Network

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
 
**Questions**
* What are some tools we can use to test network throughput? 

**Objectives**
* Learn about some of the tools used to test network performance. 

</div>

## Network (Only) Evaluation

### Throughput testing
<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Iperf3 (as distinct from "iperf" which is v2 or less)**
<hr/>

> 
>  * [https://software.es.net/iperf/](https://software.es.net/iperf/)
>  * [https://github.com/esnet/iperf](https://github.com/esnet/iperf)
>  * Pre-compiled binaries for (everything)
>    * [https://iperf.fr/iperf-download.php](https://iperf.fr/iperf-download.php)
</div>

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **nuttcp**
<hr/>

> 
>  * [http://nuttcp.org/]([http://nuttcp.org/)
>  * Much overlap with iperf3
>  * Allows "3rd party" operation where one machine can initiate tests between 2 other machines
</div>

### perfSONAR test nodes

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **Provides test endpoints**
<hr/>
> 
>  * iperf3
>  * owping/ping
>  * traceroute/tracepath
</div>

* Academic and research centric
* Many servers around the world
* Multiple servers within UH Net
* You can install the clients on Linux laptop
  * Which allows you to control remote servers
* perfSONAR toolkit is available as a Docker Container, which will work on Linux-based Docker engines. Getting the networking side working on MacOS or Windows (or WSL) is complicated, if at all possible

### perfSONAR installation options

[https://docs.perfsonar.net/install_options.html](https://docs.perfsonar.net/install_options.html)

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep30.png" alt="Node anatomy" caption="" %}

### LibreSpeedTest

* [https://github.com/librespeed/speedtest](https://github.com/librespeed/speedtest)
* Take this code and drop it into a directory on any web server
* It will provide a browser-based throughput estimate for a path

<div class="alert alert-info" role="alert" markdown="1">

>* I have one in my house
>* UH has one on Manoa Campus
</div>


 * [http://speedtest.uhnet.net](http://speedtest.uhnet.net)

### LibreSpeedTest On A Home Network

{% include figure.html url="" file="/morea/data-movement/fig/ep31.png" width=500px alt="" caption="" %}

   
### Ookla Speedtest (speedtest.net)

* Allows you to test to many points around the world from a web browser
  * [https://www.speedtest.net/](https://www.speedtest.net/)
  * Allow page to load and choose: "Change Server"
* Also offers a command line version
  * [https://www.speedtest.net/apps/cli](https://www.speedtest.net/apps/cli)
    * Which could be used to test from a remote machine via a terminal interface
>
>* Important to recognize that it focuses on testing your tester's Internet connectivity, possibly from multiple server locations
>* Distinct from testing between your location and a specific location
>* There are Ookla Speedtest servers at some universities, and if you test from a U. Hawaii campus to those servers, they should use REN paths
>* Typically, an ISP hosted server will use commodity paths

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

  * Many times data transfer is impacted by factors other than the networks, but it helps to know how to test the network. 
</div>

{% include next-button.html
  top-label="Processes and Queues ->"
  bottom-label="2:30pm"
  url="/morea/data-movement/experience-processes-and-queues.html" %}
