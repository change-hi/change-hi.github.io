---
title: "6. FAIR: Accessible"
published: true
morea_id: Accessible
morea_type: experience
morea_summary: "What is a protocol? What types of protocol are FAIR?"
morea_sort_order: 6
morea_labels:
  - 2:35pm
morea_enable_toc: true
---

# FAIR: Accessible

This section will describe what it means for research to be accessible

## For data & software to be accessible:

(Meta)data are retrievable by their identifier using a standardized communications protocol:  
* the protocol is open, free, and universally implementable  
* the protocol allows for an authentication and authorization procedure, where necessary  
* metadata remain accessible, even when the data are no longer available


## What is a protocol?

Simply put, it's an access method of exchanging data over a computer network. Each protocol has its rules for how data is formatted, compressed, checked for errors. Research repositories often use the OAI-PMH or REST API protocols to interface with data in the repository. The following image from [TutorialEdge.net: What is a RESTful API by Elliot Forbes](https://tutorialedge.net/general/what-is-a-rest-api/) provides a useful overview of how RESTful interfaces work:

{% include figure.html url="" max-width="80%"
file="/morea/fair/fig/rest-api.png"
alt="TutorialEdge.net: What is a RESTful API? by Elliot Forbes" caption="" %}

Hydroshare offers a REST API protocol which will enable many of the functions that are accessible through the web user interface, to be done programmatically:

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>
See the <a href="https://www.hydroshare.org/hsapi">Hydroshare REST API</a>
</div>


Wikipedia has a list of [commonly used network protocols](https://en.wikipedia.org/wiki/Lists_of_network_protocols) but check the service you are using for documentation on the protocols it uses and whether it corresponds with the FAIR Principles. For instance, see [Hydroshare's API Instructions](https://help.hydroshare.org/introduction-to-hydroshare/getting-started/use-the-api/) page.

## Contributor information

Alternatively, for sensitive/protected data, if the protocol cannot guarantee secure access, an e-mail or other contact information of a person/data manager should be provided, via the metadata, with whom access to the data can be discussed. The [DataCite metadata schema](https://schema.datacite.org/) includes contributor type and name as fields where contact information is included. Collaborative projects such as [THOR](https://project-thor.readme.io/), [FREYA](https://www.project-freya.eu/en/resources), and [ODIN](https://odin-project.eu/project-outputs/deliverables/) are working towards improving the interoperability and exchange of metadata such as contributor information.

## Author disambiguation and authentication

Across the research ecosystem, publishers, repositories, funders, research information systems, have recognized the need to address the problem of author disambiguation. The illustrative example below of the many variations of the name _Jens Åge Smærup Sørensen demonstrations_ the challenge of wrangling the correct name for each individual author or contributor:

{% include figure.html url="https://slideplayer.com/13579783/82/images/5/Jens+%C3%85ge+Sm%C3%A6rup+S%C3%B8rensen.jpg" max-width="80%"
file="https://slideplayer.com/13579783/82/images/5/Jens+%C3%85ge+Sm%C3%A6rup+S%C3%B8rensen.jpg"
alt="Jens Åge Smærup Sørensen" caption="" %}

Thankfully, a number of research systems are now integrating ORCID into their authentication systems. Zenodo provides the login ORCID authentication option. Once logged in, your ORCID will be assigned to your authored and deposited works.

## Create a Hydroshare Account

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Create a hydroshare account**
<hr/>

If you haven't already, please create a Hydroshare account now:

1. [Register](https://www.hydroshare.org/sign-up/) for Hydroshare.
2. You will receive a confirmation email. Click the link in the email...
3. Go to [Hydroshare](https://www.hydroshare.org) and select Log in.

{% include figure.html url="" max-width="80%"
file="/morea/fair/fig/hydrosharesignup.png"
alt="Hydroshare Registration" caption="" %}

</div>

## Understand if something is open, free, and universally implementable

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: ORCID and Accessibility**
<hr/>

ORCID features a [principles page](https://orcid.org/about/what-is-orcid/principles) where we can assess where it lies on the spectrum of these criteria. Can you identify statements that speak to these conditions: open, free, and universally implemetable?

<details>
  <summary>Solution</summary>
<ol>
<li>ORCID is a non-profit that collects fees from its members to sustain its operations [Creative Commons CC0 1.0 Universal (CC0)](https://tldrlegal.com/license/creative-commons-cc0-1.0-universal) license releases data into the public domain, or otherwise grants permission to use it for any purpose</li>
<li>It is open to any organization and transcends borders</li>
</ol>

Followup Questions:
<ul>
<li>Where can you download the freely available data?</li>
<li>How does ORCID solicit community input outside of its governance?</li>
<li>Are the tools used to create, read, update, delete ORCID data open?</li>
</ul>
</details>
</div>


## Tombstones, a very grave subject

There are a variety of reasons why a placeholder with metadata or tombstone of the removed research object exists including but not limited to staff removal, spam, request from owner, data center does not exist is still, etc. A tombstone page is needed when data and software is no longer accessible. A tombstone page communicates that the record is gone, why it is gone, and in case you really must know, there is a copy of the metadata for the record. A tombstone page should include: DOI, date of deaccession, reason for deaccession, message explaining the data center's policies, and a message that a copy of the metadata is kept for record keeping purposes as well as checksums of the files.

DataCite offers [statistics](https://stats.datacite.org/) where the failure to resolve DOIs after a certain number of attempts is reported (see [DataCite statistics support page](https://support.datacite.org/docs/datacite-statistics)for more information). In the case of Zenodo and the GitHub issue above, the hidden field reveals thousands of records that are a result of spam.

{% include figure.html url="" max-width="80%"
file="/morea/fair/fig/datacite_statistics.png"
alt="DataCite Statistics Page" caption="" %}

If a DOI is no longer available and the data center does not have the resources to create a tombstone page, DataCite provides a generic [tombstone page](https://support.datacite.org/docs/tombstone-pages).

**See the following tombstone examples:**

- Zenodo tombstone: "https://zenodo.org/record/1098445"
- Figshare tombstone: "https://figshare.com/articles/Climate_Change/1381402"

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>
The content of this chapter was adapted from: [https://librarycarpentry.org/lc-fair-research](https://librarycarpentry.org/lc-fair-research).
</div>

{% include next-button.html top-label="FAIR: Interoperable ->" bottom-label="2:45pm" url="/morea/fair/07-Interoperable.html" %}
