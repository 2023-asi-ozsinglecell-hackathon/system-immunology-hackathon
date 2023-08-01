---
title: Hackathon Challenges
nav: Challenges
---

## Data QC / Visualisation / Setting the benchmark for an API

Topics pertaining to performing quality control on the data, visualising clones, and developing the APIs to support this.

This includes:

* Developing the appropriate data structure to deal with large volume of single-cell clonality data.
* Extending Bioconductor's SingleCellExperiment S4 class in R to include a slot for storing barcode information.
* Extending the concept of meta-cell in scRNAseq to meta-clone.
* Developing APIs to perform data QC and to assess the results.
* Developing an API to better visualise expanded clones and pedigrees in scRNAseq datasets.
* Visualisation of pedigrees and framework for annotation (div number, state, etc)

## Differential expression within and between clones

Topics pertaining to performing differential expression and abundance analysis between the clones.

This includes:
* Quantifying intra- and inter-clonal transcriptional signatures.
* Can we quantify clonal expansion and proliferation capacity?
* Determining how to best quantify the distribution of clonally related cells across different cell states / tissues.
* Determining how to show clonal relationships while respecting GEX similarity, or TCR/BCR similarity at a scalable fashion.


## Identify clonally related cells based on transcriptome similarity

Topics pertaining identifying clonally related cells based on their transcriptomic profile (independent of their barcodes).

This includes:
* Barcode free detection of clones i.e. are there genes that are unrelated to cell state, but heritable clonally?
* Overcoming the limits of sampling - how to deal with missing clonal members.
* How to deal with “soup” V(D)J contigs?
* Are there better ways to understand the molecular determinants of clonal fate beyond linear regression?

