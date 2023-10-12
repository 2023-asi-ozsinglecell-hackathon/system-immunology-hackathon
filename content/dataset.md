---
title: Dataset
nav: Dataset
---

# TLDR

The datasets can be downloaded from [Zenodo](https://zenodo.org/record/8303282).

The following files are in the Zenodo repository:

* The raw celllranger output (filename: raw_cellranger_output.zip)
* The pre-processed data (filename: preprocessed_data.zip).
    * Within the zip file, there are h5ad, SingleCellExperiment, and Seurat object of the pre-processed data.
    * The samples have all been concatenated into one single object.

The scripts used to pre-process the data is available on [Github](https://github.com/2023-asi-ozsinglecell-hackathon/data_preprocessing).

# Background information about the dataset 

Biological summary and experimental background behind the dataset.

## The immune response and B cell biology

The immune system is our body’s defence against infection. A particularly important cell type in our immune system are B cells that make antibodies to recognise and fight foreign bacteria or viruses. After encountering these foreign invaders, B cells are activated and can then clonally expand. They can either differentiate immediately into short-lived plasma cells, or undergo a process call the germinal centre (GC) reaction. Within the GC, with the help from antigen-specific T cells, B cells can undergo further cycles of clonal expansion and selection before differentiating into antibody-secreting plasma cells or memory B cells, which are capable of being reactivated upon antigen re-exposure. Understanding why and how different B cell clones make different cell fate decisions during this process is a longstanding area of interest in the field.

## Immunoglobulin genes can act as endogenous barcodes in B cells

All B cells express the immunoglobulin (Ig) genes that encode antibody proteins (also known as B cell receptor) and these Ig genes can act as endogenous barcodes for clonal identity. There are three Ig loci and typically, each B cell will express IgH and either IgL or IgK. During development in the bone marrow, the Ig loci must be recombined from many different Variable (V), Diversity (D) or Joining (J) genes encoded in the DNA, retaining only one of each gene (V, D and J for IgH; V and J for IgK/IgK). For example, the human Ig heavy chain region contains 44 V gene segments, 27 D gene segments and 6 J gene segments that are randomly recombined. During this process, additional insertions and deletions can occur between the VDJ genes, further increasing the complexity of the recombined Ig locus. The estimated potential number of recombinant products is 1011 and this is important for the ability of the immune system to recognise an enormous diversity of foreign pathogens.
While this is a complicated biological process, for the purposes of this Hackathon, we will treat the VDJ gene sequence as an endogenous barcode that allows us to compare clonally-related and -unrelated cells with one another.

## The issue of sampling: how many clones is enough?

One major challenge with comparing clonally-related cells identified through any method relates to whether one can sample enough members for different clones to accurately reflect the entire clonal population. For example, if an expanded clone (or clonotype) consists of 100 clonally-related cells, but we only examine 5 of them, are we accurately assessing the properties of that clone? This is especially a challenge in the immune system, where many single-cell datasets examining B cell clonality are derived from peripheral blood or tissues, and out of the billions of B cells in the body, we can only sample several thousand. This means the majority of “expanded clones” identified in existing datasets contain only 2-4 members, limiting the biological questions we can ask about properties of different clones. It also is a barrier to the development of new tools in this area.

# The datasets
For this Hackathon, we have performed an experiment to try and overcome the above biological and technical challenge. Using mouse B cells as a model, and their endogenous VDJ barcodes as a method to identify clonally related cells, we expanded a small number (5,000) of mouse B cells in cell culture and then performed single-cell RNA and VDJ sequencing after several days of expansion. Two different datasets were generated to answer different biological and technical questions, CpG dataset and CD40 dataset. There are two time-points for the CD40 dataset and one time-point for the CpG dataset. There are two replicates for each dataset (2 replicates for CpG, 2 replicates for each of the two time-points in the CD40 dataset). The datasets are sequenced across 2 different batches:

| Sample  | Batch  | Replicate  | Dataset type  | Timepoint  | No. of cells sequenced |
| --- | --- | --- | --- | --- | --- |
BC1-CpG | 1 | 1 | CpG | 72h | 14,331
BC2-CpG | 1 | 2 | CpG | 72h | 10,269
BC1-CD40-72h | 1 | 1 | CD40 | 72h | 6,496
BC2-CD40-72h  | 1 | 2 | CD40 | 72h | 5,036
BC1-CD40-120h | 2 | 1 | CD40 | 120h | 9,221
BC2-CD40-120h | 2 | 2 | CD40 | 120h | 8,295

## CpG dataset - Comparison of clonally-expanded cells with other expanded clones
In this experiment, we aimed to capture B cells that have expanded, but not undergone differentiation. 

Mouse naïve B cells (5,000 cells) were stimulated in cell culture with CpG for 72 hours in 2 biological replicates. CpG activates B cells to proliferate through TLR signalling but does not result in differentiation of the B cells (Turner et al., Journal of Immunology, 2004). At 72 hours, the cells had expanded by 7.8-fold and 10,000 cells per replicate were loaded onto the 10X Genomics platform. 

Based on previous experiments with this system, clonally-related cells are significantly more likely to divide (proliferate) at the same rate and for a similar number of divisions (approximately 1-5 divisions), than cells that are not clonally related to one another. This new dataset will allow us to explore this and quantify if there are unique transcriptional signatures between different expanded clones that may explain this. 

Below are some UMAP plots of the data (steps taken to produce them are described in the next section). Each dot is a cell. 

{% include figure.html img="cpg/umap_sample.png" caption="UMAP plot coloured by the sample the cell came from." width="75%" %}

{% include figure.html img="cpg/umap_annot.png" caption="UMAP plot coloured by the cell type the cell belongs to. The annotation was done manually." width="75%" %}

{% include figure.html img="cpg/umap_clone.png" caption="UMAP plot coloured by the clonotype of the cells. Specifically, cells that belong to the top 10 most abundant clonotypes are given distinct colours, while cells belonging to clonotypes outside of this top 10 are coloured in gray." width="75%" %}

The table below shows the number of cells for a given clonotype:

| clone_id_by_size | No. of cells |
| --- | --- |
2 | 21
3 | 17
5 | 16
6 | 15
8 | 11
7 | 15
9 | 15
4 | 15
10 | 15

{% include figure.html img="cpg/violin_clonotype_size.png" caption="Violin plot shows the distribution of the clonotype size for each sample." width="75%" %}


















