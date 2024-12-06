---
layout: tutorial_hands_on
title: Import & Analyse Public Data
abbreviations:
  EBI: European Bioinformatics Institute
zenodo_link: ''
questions:
- How do you import datasets from the EBI SCXA using Galaxy?
- What are the steps to execute a pre-built workflow in Galaxy?
- How can you modify analysis parameters to improve cluster quality?
- How do you annotate cell types using marker genes in your dataset?
- What techniques can be used to compare cell populations under different conditions?
objectives:
- Understand and Retrieve Public Bioinformatics Data.
- Apply Analysis Workflows to Genomic Data.
- Evaluate and Interpret Biological Data Analysis
- Analyze and Compare Cellular Populations
time_estimation: "2H"
key_points:
- Access and import datasets from EBI SCXA using Galaxy tools, leveraging public data with rich metadata.
- Utilize pre-built workflows in Galaxy to automate and simplify bioinformatics analysis of selected datasets.
- Evaluate clustering results, modify analysis parameters, and annotate cell types to interpret biological significance.
- Compare cell populations under different conditions (e.g., disease vs. healthy) to draw insights into biological effects.
tags:
- EBI
- single cell
priority: 4
contributions:
  authorship:
    - nomadscientist
    - khaled196
    -
    - poterlowicz-lab
requirements:
  - type: "internal"
    topic_name: single-cell
    tutorials:
      - EBI-retrieval

recordings:
  - speakers:
    - hexhowells
    date: '2024-09-12'
    length: 18M54S
    youtube_id: "Yx7m7Uh4tVg"

---


> <agenda-title></agenda-title>
>
> In this tutorial, we will cover:
>
> 1. TOC
> {:toc}
>
{: .agenda}

# Retrieve Genetec Data From EBI Using Galaxy

The European Bioinformatics Institute’s Single Cell Expression Atlas has a ton of freely available, well curated datasets. This curation is key - the datasets often have clear metadata (such as ‘disease’ or ‘sex’) which is not always the case with datasets. You will now get to pick one and analyse it!

> <hands-on-title>Retrieving data from Single Cell Expression Atlas</hands-on-title>
>
> Follow the {[Importing files from public atlases tutorial]( {% link topics/single-cell/tutorials/scrna-import-and-analyse/tutorial.md %} ) the data for the analsys. 
>
{: .hands_on}

The data can also be downoladed directly from the EBI website {% cite EBI SCXA site %}.


> <hands-on-title>Locate Data on the EBI Website</hands-on-title>
>
> 1. Go to the (EBI SCXA site)[https://www.ebi.ac.uk/gxa/sc/experiments]
> 2. Search for a dataset that interests you by inputting terms into the “Search all columns:” box. {% icon warning %} Choose a dataset between 1000 and 10,000 cells. Analyses with more cells can take a long time!
> 3. To extract the genomic from the datasets You need to identify the Accession number wich you can find in the URL link. For example the Accession number for this link "https://www.ebi.ac.uk/gxa/sc/experiments/E-MTAB-7704/results/tsne"
> is **E-MTAB-7704**. For this training you can pick your own dataset or use the Accession number for the dataset in the link above
{: .hands_on}


> <hands-on-title>Use the Accession number Download Data from the EBI Website</hands-on-title>
>
> 1.Import this [workflow](https://singlecell.usegalaxy.eu/published/workflow?id=f05754467a439134) that will Download the data from EBI
> 
> {% snippet faqs/galaxy/workflows_import.md %}
> 
> 2. Run the workflow using the Accession number that you have optained from the EBI dataset link.
> 
> {% snippet faqs/galaxy/workflows_run.md %}
>
> All datasets are different! Some may have mitochondrial data easily found, but in some species, this is not the case. You may have to perform troubleshooting and/or adapt the analysis to your dataset of interest!
{: .hands_on}

There are many ways to learn more from public data than the original authors - there is simply too much information in any given experiment to completely publish in one study (or analyse in one week!)!

# Evaluate your analysis

We have used a prebuild workflow to analyse the data. However, were the base parameter settings in that workflow the best for the dataset?

> <hands-on-title>Analysis Evaluation</hands-on-title>
>
> 1. Inspect the different parameters that you set during the Filter, plot & explore tutorial for this dataset.
> Are you happy with the default settings? Look at the quality control plots. Does this default pipeline make sense? 
> 
> 2. Test different parameters in line with what you learned in the Filter, plot & explore tutorial.
> > <tip-title>Importing data via links</tip-title>
> >
> > * Copy the link location
> > * Open the Galaxy Upload Manager
> > * Select **Paste/Fetch Data**
> > * Paste the link into the text field
> > * Press **Start**
> {: .tip}
>
>
> 
> {% snippet faqs/galaxy/workflows_run.md %}
>
> All datasets are different! Some may have mitochondrial data easily found, but in some species, this is not the case. You may have to perform troubleshooting and/or adapt the analysis to your dataset of interest!
{: .hands_on}

