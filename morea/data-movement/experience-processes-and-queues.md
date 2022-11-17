---
title: "4. Processes and Queues"
published: true
morea_id: experience-processes-and-queues
morea_type: experience
morea_summary: "Understand how data actually moves between machines and explain queues and buffers."
morea_sort_order: 4
morea_labels:
  - 2:30pm
morea_enable_toc: true
---
<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>
 
**Questions**
* What are Queues/Buffers?
* How does data actually move from machine to machine?

**Objectives**
* Understand the processes involved in transfering data from one machine to another.  


</div>

# Queues (also known as buffers)

Queues are places where things arrive to wait for something

Data waits in queues for a chance to be transmitted further

> ## Queues are the reason that everything in the universe isn't stuck waiting for everything else.

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep40.jpg" alt="Node anatomy" caption="" %}
(Attribution: © Vulphere Wikimedia Commons CC BY 4.0 https://creativecommons.org/licenses/by/4.0/deed.en)

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep41.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep42.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep43.png" alt="Node anatomy" caption="" %}

{% include figure.html url="" max-width="75%" file="/morea/data-movement/fig/ep44.png" alt="Node anatomy" caption="" %}


# Notable Points

* Data moves by processes:
  * Enqueuing data
  * Dequeuing data
* Some Network queues have "easy" adjustments because
  * the large variation in latency
  * Optimizations vary by use-case
* Storage systems benefit from design choices
* Most defaults support many users sharing a resource
* Our use case is more about committing entire machines to a single purpose

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

  * There are many processes in transfering data that can cause bottlenecks and degrade performance, the network is only one of many of these processes. 
</div>

{% include next-button.html
  top-label="Transmission Control Protocol (TCP) ->"
  bottom-label="2:40pm"
  url="/morea/data-movement/experience-transmission-control-protocol.html" %}