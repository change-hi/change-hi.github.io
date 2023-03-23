---
title: "5. Tapis UI"
published: true
morea_id: experience-smart-data-collection-tapis-ui
morea_type: experience
morea_summary: "How can we use Tapis UI to view sensor station data?"
morea_sort_order: 2
morea_labels:
  - 3:30pm - 3:45pm
---

# 4. Tapis UI

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Overview**
<hr/>

**Questions**
  * How can we use Tapis UI to view sensor station data?

**Objectives**
  * How to view Streams data via Tapis UI.
</div>

## Overview

In addition to the tapipy library for Python, Tapis also provides a TypeScript library for interacting with the Tapis APIs. Tapis UI is a modular web application built in React that leverages this TypeScript library to provide a web-based user interface for interacting with Tapis. The Streams component of the UI allows us to query and view Measurements created by the Streams API.

## Viewing Streams Measurements

To try out Tapis UI, go [here](https://ci-tracs.github.io/tapis_ui_training/){:target="_blank"} and use the Tapis credentials you were provided to login.

Navigate to the Streams component:

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/tapis_ui_nav.png" alt="Go to Streams" caption="" %}

Then select the Project, Site, and Instrument you created with the Jupyter notebook. This should pull the measurements that were created for each variable and creates a graph displaying the values. The returned values can also be filtered using the controls along the top of the measurements.

{% include figure.html url="" max-width="50%" file="/morea/smart-data-collection/fig/tapis_ui_measurments.png" alt="View Measurments" caption="" %}

<div class="alert alert-success mt-3" role="alert" markdown="1">
<i class="fa-solid fa-globe fa-xl"></i> **Key Points**
<hr/>

* Tapis UI provides a basic user interface on top of the Tapis TypeScript Library for interacting with the Tapis APIs.
* The streams component allows users to query and view measurements pushed into the Streams API.

</div>


{% include next-button.html
top-label="Assessment ->"
bottom-label="3:45pm"
url="/morea/smart-data-collection/assessment-smart-data-collection.html" %}
