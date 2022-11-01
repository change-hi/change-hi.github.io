---
title: "10. Public repositories"
published: true
morea_id: FairRepositories
morea_type: experience
morea_summary: "Where can I deposit datasets? What are general data repositories? How to find a repository?"
morea_sort_order: 10
morea_labels:
  - 3:10pm
morea_enable_toc: true
---

# Public repositories
This section will describe what are public repositories.

## What are research data repositories?

Research data repositories are online repositories that enable the preservation, curation and publication of research 'products'. These repositories are mainly used to deposit research 'data'. However, the scope of the repositories is broader as we can also deposit/publish 'code' or 'protocols' (as we saw with protocols.io).

There are general "data agnostic" repositories, for example:

- [Dryad](https://datadryad.org),
- [Zenodo](https://zenodo.org),
- [FigShare](https://figshare.com),

Or domain specific, for example:

- [UniProt](https://www.uniprot.org/) protein data,
- [GenBank](https://www.ncbi.nlm.nih.gov/genbank/) sequence data,
- [MetaboLights](https://www.ebi.ac.uk/metabolights/) metabolomics data
- [GitHub](https://github.com/) for code.
- [Hydroshare](https://www.hydroshare.org/) for water data.

Research outputs should be submitted to discipline/domain-specific repositories whenever it is possible. When such a resource does not exist, data should be submitted to a 'general' repository.
Research data repositories are a key resource to help in data FAIRification as they
assure Findability and Accessibility.

## What makes it FAIR?

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: What makes it FAIR?**
<hr/>

Have a look at the following record for data set in Hydroshare repository:
[Hydroshare](https://www.hydroshare.org/resource/96310f82dd5247ba8201955750093923).
What elements make it FAIR?

<details>
  <summary>Solution</summary>
<p>
The elements that make this deposit FAIR are:
</p>
<p>
Findable (persistent identifiers, easy to find data and metadata):
</p>

<ul>
<li>F1. (Meta)data are assigned a globally unique and persistent identifier - YES</li>
<li>F2. Data are described with rich metadata (defined by R1 below)- YES</li>
<li>F3. Metadata clearly and explicitly include the identifier of the data they describe - YES</li>
<li>F4. (Meta)data are registered or indexed in a searchable resource - YES</li>
</ul>


<p>
Accessible (The (meta)data retrievable by their identifier using a standard web protocols):</p>

<ul>
<li>A1. (Meta)data are retrievable by their identifier using a standardised communications protocol - YES</li>
<li>A2. Metadata are accessible, even when the data are no longer available - YES</li>
</ul>


<p>
Interoperable (The format of the data should be open and interpretable for various tools):
</p>

<ul>
<li>I1. (Meta)data use a formal, accessible, shared, and broadly applicable language for knowledge representation. - YES</li>
<li>I2. (Meta)data use vocabularies that follow FAIR principles - PARTIALLY</li>
<li>I3. (Meta)data include qualified references to other (meta)data - YES</li>
</ul>


<p>
Reusable (data should be well-described so that they can be replicated and/or combined in different settings, reuse states with a clear licence):
</p>

<ul>
<li>R1. (Meta)data are richly described with a plurality of accurate and relevant attributes - YES</li>
<li>R1.1. (Meta)data are released with a clear and accessible data usage license - YES</li>
<li>R1.2. (Meta)data are associated with detailed provenance - YES</li>
<li>R1.3. (Meta)data meet domain-relevant community standards - YES/PARTIALLY</li>
</ul>

</details>
</div>

## Minimal data set

Minimal data set to consist of the data required to replicate all study findings reported
in the article, as well as related metadata and methods.

- The values behind the means, standard deviations and other measures reported;
- The values used to build graphs;
- The points extracted from images for analysis.

(no need for raw data if the standard in the field is to share data that have been processed)

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>
See the [PLOS guidelines for data availability](https://journals.plos.org/plosbiology/s/data-availability)
</div>

## How do we choose a research data repository?

As a general rule, your research needs to be deposited in discipline/data specific repository. If no specific repository can be found, then you can use a generalist repository. Having said this, there are tons of data repositories to choose from. Choosing one can be time consuming and challenging as well.
So how do you go about finding a repository:

- Check the publisher's / funder' recommended list of repositories, some of which can be found below:

  - [BioMed Central / Springer Nature](https://www.springernature.com/gp/authors/research-data-policy/recommended-repositories)
  - [eLife](https://submit.elifesciences.org/html/elife_author_instructions.html#policies)
  - [Elsevier](https://www.elsevier.com/about/policies/research-data)
  - [EMBO Press](https://www.embopress.org/page/journal/14602075/authorguide#datadeposition)
  - [F1000 Research](https://f1000research.com/for-authors/data-guidelines)
  - [GIGAscience - OUP](https://academic.oup.com/gigascience/pages/instructions_to_authors)
  - [PLoS](https://journals.plos.org/plosbiology/s/recommended-repositories)
  - [Scientific Data - Nature](https://www.nature.com/sdata/policies/repositories)
  - [Taylor and Francis](https://authorservices.taylorandfrancis.com/data-sharing-policies/repositories/)
  - [BBSRC](https://bbsrc.ukri.org/research/resources/)
  - [NERC](https://nerc.ukri.org/research/sites/environmental-data-service-eds/policy/)
  - [Royal Society](https://royalsociety.org/journals/ethics-policies/data-sharing-mining/)
  - [Wellcome Open Research](https://wellcomeopenresearch.org/for-authors/data-guidelines)

- Check [Fairsharing recommendations](https://fairsharing.org/recommendations/?q=)
  - alternatively, check the [Registry of research data repositories - re3data](https://www.re3data.org/)

## Find a repository

<div class="alert alert-secondary" role="alert" markdown="1">
<i class="fa-solid fa-user-pen fa-xl"></i>  **Exercise: Public Repository**
<hr/>
Using what you've learned so far:
1. Find a repository for genomics data.
2. Find a repository for microscopy data.  

<details>
  <summary>Solution</summary>

<ul>
<li>GEO/SRA and ENA/ArrayExpress are good examples. Interestingly these repositories do not issue a DOI.  </li>
<li>IDR is good examples.  </li>
</ul>
A list of UoE BioRDM's recommended data repositories can be found <a href="https://www.wiki.ed.ac.uk/display/RDMS/Suggested+data+repositories">here</a>.

</details>
</div>

## What comes first? the repository or the metadata?

Finding a repository first may help in deciding what metadata to collect and how!

## Extra features

It is also worth considering that some repositories offer extra features, such as running simulations or providing visualisation. For example, [FAIRDOMhub](https://fairdomhub.org/) can run model simulations and has project structures. Do not forget to take this into account when choosing your repository. Extra features might come in handy.

## Can GitHub be cited?

To make your code repositories easier to reference in academic literature, you can create persistent identifiers for them. Particularly, you can use the data archiving tool in Zenodo to archive a GitHub repository and issue a DOI for it.

## Evaluating a research data repository

You can evaluate the repositories by following this criteria:
- who is behind it, what is its funding
- quality of interaction: is the interaction for purposes of data deposit or reuse efficient, effective and satisfactory for you?
- take-up and impact: what can I put in it? Is anyone else using it? Will others be able to find stuff deposited in it? Is the repository linked to other data repositories so I don't have to search there as well? Can anyone reuse the data? Can others cite the data, and will depositing boost citations to related papers?
- policy and process: does it help you meet community standards of good practice and comply with policies stipulating data deposit?

<div class="alert alert-info" role="alert" markdown="1">
<i class="fa-solid fa-circle-info fa-xl"></i> **For more information**
<hr/>

An interesting take can be found at Peter Murray-Rust's blog post [Criteria for successful repositories](https://blogs.ch.cam.ac.uk/pmr/2011/08/19/criteria-for-successful-repositories/).

The content of this chapter was adapted or inspired by:
* [FAIR principles](https://www.go-fair.org/fair-principles/)
* [BioRDM suggested data repositories](https://www.wiki.ed.ac.uk/display/RDMS/Suggested+data+repositories)
* [DCC - How can we evaluate data repositories?](https://www.dcc.ac.uk/news/how-can-we-evaluate-data-repositories-pointers-dryaduk)
* [Criteria for succesful repositories](https://blogs.ch.cam.ac.uk/pmr/2011/08/19/criteria-for-successful-repositories/)
</div>

{% include next-button.html top-label="Exercises ->" bottom-label="3:20pm" url="/morea/fair/10-Exercises.html" %}
