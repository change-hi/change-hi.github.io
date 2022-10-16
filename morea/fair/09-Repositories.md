---
title: "Public repositories"
published: true
morea_id: FairRepositories
morea_type: experience
morea_summary: "Where can I deposit datasets? What are general data repositories? How to find a repository?"
morea_sort_order: 10
morea_labels:
  - 8 min (Teaching)
  - 2 min (Exercise)
morea_enable_toc: true
---

## What are research data repositories?

(13 min teaching)
Research data repositories are online repositories that enable the preservation, curation and publication of research 'products'. These repositories are mainly used to deposit research 'data'. However, the scope of the repositories is broader as we can also deposit/publish 'code' or 'protocols' (as we saw with protocols.io).

There are general "data agnostic" repositories, for example:

- [Dryad](http://datadryad.org),
- [Zenodo](http://zenodo.org),
- [FigShare](http://figshare.com),
- [Dataverse](http://thedata.org).

Or domain specific, for example:

- [UniProt](https://www.uniprot.org/) protein data,
- [GenBank](https://www.ncbi.nlm.nih.gov/genbank/) sequence data,
- [MetaboLights](https://www.ebi.ac.uk/metabolights/) metabolomics data
- [GitHub](https://github.com/) for code.
- [Hydroshare](https://www.hydroshare.org/) for water data.

Research outputs should be submitted to discipline/domain-specific repositories whenever it is possible. When such a resource does not exist, data should be submitted to a 'general' repository.
Research data repositories are a key resource to help in data FAIRification as they
assure Findability and Accessibility.

> ## Exercise 9: Public general record (8 min)
>
> Have a look at the following record for data set in Hydroshare repository:
> [Hydroshare](http://www.hydroshare.org/resource/96310f82dd5247ba8201955750093923).
> What elements make it FAIR?
>
> > ## Solution
> >
> > The elements that make this deposit FAIR are:
> >
> > Findable (persistent identifiers, easy to find data and metadata):
> >
> > - F1. (Meta)data are assigned a globally unique and persistent identifier - YES
> > - F2. Data are described with rich metadata (defined by R1 below)- YES
> > - F3. Metadata clearly and explicitly include the identifier of the data they describe - YES
> > - F4. (Meta)data are registered or indexed in a searchable resource - YES
> >
> > Accessible (The (meta)data retrievable by their identifier using a standard web protocols):
> >
> > - A1. (Meta)data are retrievable by their identifier using a standardised communications protocol - YES
> > - A2. Metadata are accessible, even when the data are no longer available - YES
> >
> > Interoperable (The format of the data should be open and interpretable for various tools):
> >
> > - I1. (Meta)data use a formal, accessible, shared, and broadly applicable language for knowledge representation. - YES
> > - I2. (Meta)data use vocabularies that follow FAIR principles - PARTIALLY
> > - I3. (Meta)data include qualified references to other (meta)data - YES
> >
> > Reusable (data should be well-described so that they can be replicated and/or combined in different settings, reuse states with a clear licence):
> >
> > - R1. (Meta)data are richly described with a plurality of accurate and relevant attributes - YES
> >   - R1.1. (Meta)data are released with a clear and accessible data usage license - YES
> >   - R1.2. (Meta)data are associated with detailed provenance - YES
> >   - R1.3. (Meta)data meet domain-relevant community standards - YES/PARTIALLY
> >
> > {: .solution}
> > {: .challenge}

(4 min discussion)

> ## Minimal data set
>
> Minimal data set to consist of the data required to replicate all study findings reported
> in the article, as well as related metadata and methods.
>
> - The values behind the means, standard deviations and other measures reported;
> - The values used to build graphs;
> - The points extracted from images for analysis.
>
> (no need for raw data if the standard in the field is to share data that have been processed)
>
> [PLOS](https://journals.plos.org/plosbiology/s/data-availability)
>
> {: .callout}

## How do we choose a research data repository?

(3 min teaching)
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

> ## Exercise 10: Finding a repository (5 min + 4 min discussion).
>
> a) Find a repo for genomics data.  
> b) Find a repo for microscopy data.  
> Note to instructor: Fairsharing gives few options, people may give different answer follow up why they selected particular ones.
>
> > ## Solution
> >
> > a) GEO/SRA and ENA/ArrayExpress are good examples. Interestingly these repositories do not issue a DOI.  
> > b) IDR is good examples.  
> > {: .solution}  
> > {: .challenge}

(6 min teaching)

A list of UoE BioRDM's recommended data repositories can be found [here](https://www.wiki.ed.ac.uk/display/RDMS/Suggested+data+repositories).

> ## What comes first? the repository or the metadata?
>
> Finding a repository first may help in deciding what metadata to collect and how!
>
> {: .callout}

> ## Extra features
>
> It is also worth considering that some repositories offer extra features, such as running simulations or providing visualisation. For example, [FAIRDOMhub](https://fairdomhub.org/) can run model simulations and has project structures. Do not forget to take this into account when choosing your repository. Extra features might come in handy.
>
> {: .callout}

> ## Can GitHub be cited?
>
> To make your code repositories easier to reference in academic literature, you can create persistent identifiers for them. Particularly, you can use the data archiving tool in Zenodo to archive a GitHub repository and issue a DOI for it.
>
> {: .callout}

## Evaluating a research data repository

You can evaluate the repositories by following this criteria:

- who is behind it, what is its funding
- quality of interaction: is the interaction for purposes of data deposit or reuse efficient, effective and satisfactory for you?
- take-up and impact: what can I put in it? Is anyone else using it? Will others be able to find stuff deposited in it? Is the repository linked to other data repositories so I don't have to search tehre as well? Can anyone reuse the data? Can others cite the data, and will depositing boost citations to related papers?
- policy and process: does it help you meet community standards of good practice and comply with policies stipulating data deposit?

> ## Resources
>
> - An interesting take can be found at Peter Murray-Rust's blog post [Criteria for succesful repositories](https://blogs.ch.cam.ac.uk/pmr/2011/08/19/criteria-for-successful-repositories/).

> ## Attribution
>
> Content of this episode was adapted or inspired by:.
>
> - [FAIR principles](https://www.go-fair.org/fair-principles/)
> - [BioRDM suggested data repositories](https://www.wiki.ed.ac.uk/display/RDMS/Suggested+data+repositories)
> - [DCC - How can we evaluate data repositories?](https://www.dcc.ac.uk/news/how-can-we-evaluate-data-repositories-pointers-dryaduk)
> - [Criteria for succesful repositories](https://blogs.ch.cam.ac.uk/pmr/2011/08/19/criteria-for-successful-repositories/)
>   {: .callout}
