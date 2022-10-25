---
title: "4. FAIR Introduction"
published: true
morea_id: FAIR_Intro
morea_type: experience
morea_summary: "What are the FAIR principles? Why should I care to be FAIR? How do I get started?"
morea_sort_order: 4
morea_labels:
  - 2:20pm
morea_enable_toc: true
---

# FAIR Introduction

The FAIR principles for research data, originally published in a [2016 Nature
paper](https://doi.org/10.1038/sdata.2016.18), are intended as "a guideline for
those wishing to enhance the reusability of their data holdings." This guideline
has subsequently been endorsed by working groups, funding bodies and
institutions.

FAIR is an acronym for Findable, Accessible, Interoperable, Reusable.

- Findable: others (both human and machines) can discover the data
- Accessible: others can access the data
- Interoperable: the data can easily be used by machines or in data analysis workflows.
- Re-usable: the data can easily be used by others for new research

The FAIR principles have a strong focus on "machine-actionability". This means
that the data should be easily readable by computers (and not only by humans).
This is particularly relevant for working with and discovering new data.

## What the FAIR principles are **not**

- A standard: The FAIR principles need to be adopted and followed as much as
  possible by considering the research practices in your field.

- All or nothing: making a dataset (more) FAIR can be done in small,
  incremental steps.

- Open data: FAIR data does not necessarily mean openly available. For
  example, some data cannot be shared openly because of privacy
  considerations. As a rule of thumb, data should be _"as open as possible, as
  closed as necessary."_

- Tied to a particular technology or tool. There might be different tools that
  enable FAIR data within different disciplines or research workflows.

## Why FAIR?

The original authors of the FAIR principles had a strong focus on enhancing
reusability of data. This ambition is embedded in a broader view on knowledge
creation and scientific exchange. If research data are easily discoverable and
re-usable, this lowers the barriers to repeat, verify, and build upon previous
work. The authors also state that this vision applies not just to data, but to
all aspects of the research process.

## What's in it for you?

FAIR data sounds like a lot of work. Is it worth it? Here are some of the benefits:

- Funder requirements
- It makes your work more visible
- Increase the reproducibility of your work
- If others can use it easily, you will get cited more often
- You can create more impact if it's easier for others to use your data


## Getting started with FAIR (climate) data

As mentioned above, the FAIR principles are intended as guidelines to increase
the reusability of research data. However, how they are applied in practice
depends very much on the domain and the specific use case at hand.

For the domain of climate sciences, some standards have already been developed
that you can use right away. In fact, you might already be using some of them
without realizing it. NetCDF files, for example, already implement some of the
FAIR principles around data modeling. But sometimes you need to find your own
way.

## Challenge for yourself - Evaluate one of your own datasets


Pick one dataset that you've created or worked with recently, and answer the
following questions:

- If somebody gets this dataset from you, would they be able to understand
  the structure and content without asking you?
- Do you know who has access to this dataset? Could somebody easily have access
  to this dataset? How?
- Does this dataset needs proprietary software to be used?
- Does this dataset have a persistent identifier or usage licence?


<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>
See the 2016 Nature article, "[The FAIR Guiding Principles for scientific data management and stewardship](https://www.nature.com/articles/sdata201618)", Wilkinson et. al.

The content in this page was adapted from: [https://esciencecenter-digital-skills.github.io/Lesson-FAIR-Data-Climate/](https://esciencecenter-digital-skills.github.io/Lesson-FAIR-Data-Climate/)
</div>

{% include next-button.html top-label="FAIR: Findable ->" bottom-label="2:25pm" url="/morea/fair/05-Findable.html" %}
