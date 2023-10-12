# ASI Systems Immunology x OzSingleCell Hackathon 2023

We are excited to announce the return of the ASI - OzSingleCell Hackathon in 2023. 
It will take place on the 23rd-25th October 2023 in Melbourne prior to the OzSingleCell annual conference (25-27th Oct). 
This year's theme is focused on "Clonal Biology" and will bring together early-career researchers and leaders in single cell genomics, clonal biology, and immunology to tackle some of the grand challenges that exist in the analysis and interpretation of clonally-related cells in single-cell genomic datasets.

Cells sharing the same clonal origins contain identical sets of genetic material and they pass this on to their progeny.
Recent advances in single-cell analysis has allowed for the simultaneous detection of the transcriptome and other modes of data to allow us to track a cell's clonality, which has revolutionised our capacity to understand single cell types and their fates and origins.
This is particularly notable in the field of immunology, particularly for studies working on clonal selection of B and T lymphocytes.
Recent advances in single-cell lineage tracing technologies have also been applied to other cell types, such as dendritic cells or cancer cells. 
Regardless of the technology used to identify clonally-related cells, or the biological system, many challenges and opportunities exist in terms of testing biologically meaningful hypothesis with such sparse and complex datasets.

The ASI - OzSingleCell Hackathon 2023 aims to bring together experimental (wet-lab) and computational (dry-lab) scientists working in the field of clonal biology, including those working with single-cell technologies like lentiviral barcoding, BCR/TCR clonotyping, and mitochondrial lineage tracing. 
Others from disparate fields such as UX/UI engineers, AI/ML, deep learning, graph neural networks, computer vision or image preprocessing, causal inference are also encouraged to attend.
Data challenges may involve developing new methods for intra-/inter-clonal gene expression signatures, data architecture of clonotype information, or data visualisation.

By spending time in a room together, this event aims to foster new collaborations, connections and tools to build on Australia's capabilities in single-cell genomics. The intended outcomes for this workshop are:

* Seeding of new projects and collaborations
* New tools for single-cell clonality visualisation and/or analysis
* Publication of a Grand Challenges summary

## Important details

**Hackathon**: Monday 23rd Oct 12.30-late and Tuesday 24th Oct 9-4pm, followed by summary presentations the morning of 25th prior to Oz Single Cell conference (25-27th October).

**Data release**: Please go to the [main website](https://2023-asi-ozsinglecell-hackathon.github.io/system-immunology-hackathon/) for details.

## Challenges

### Data QC / Visualisation / Setting the benchmark for an API

Topics pertaining to performing quality control on the data, visualising clones, and developing the APIs to support this.

This includes:

* Developing the appropriate data structure to deal with large volume of single-cell clonality data.
* Extending Bioconductor's SingleCellExperiment S4 class in R to include a slot for storing barcode information.
* Extending the concept of meta-cell in scRNAseq to meta-clone.
* Developing APIs to perform data QC and to assess the results.
* Developing an API to better visualise expanded clones and pedigrees in scRNAseq datasets.
* Visualisation of pedigrees and framework for annotation (div number, state, etc)

### Differential expression within and between clones

Topics pertaining to performing differential expression and abundance analysis between the clones.

This includes:
* Quantifying intra- and inter-clonal transcriptional signatures.
* Can we quantify clonal expansion and proliferation capacity?
* Determining how to best quantify the distribution of clonally related cells across different cell states / tissues.
* Determining how to show clonal relationships while respecting GEX similarity, or TCR/BCR similarity at a scalable fashion.


### Identify clonally related cells based on transcriptome similarity

Topics pertaining identifying clonally related cells based on their transcriptomic profile (independent of their barcodes).

This includes:
* Barcode free detection of clones i.e. are there genes that are unrelated to cell state, but heritable clonally?
* Overcoming the limits of sampling - how to deal with missing clonal members.
* How to deal with “soup” V(D)J contigs?
* Are there better ways to understand the molecular determinants of clonal fate beyond linear regression?
