---
title: "#UCDAssemble Workshop - Friday Update"
tags: []
categories:
- blog
---
The workshop is not over yet. In this commentary, we will add topics that did
not fit yesterday's [coverage](http://www.homolog.us/blogs/blog/2013/12/19
/ucdassemble-workshop-covering-genome-assembly/). It will be updated, as we go
through various tweets.
<!--more-->

**Lex Nederbragt - Assembly: before and after**

These slides contain set of pre- and post-processing tools for genome
assembly.

** [Assembly: before and after](https://www.slideshare.net/flxlex/assembly-before-and-after) ** from **[Lex Nederbragt](http://www.slideshare.net/flxlex)**

**Jared Simpson discussed Paul Melsted's Quick and Dirty de Bruijn Code**

You can access the code from following link.

[Naive python implementation of a de Bruijn
Graph](http://pmelsted.wordpress.com/2013/11/23/naive-python-implementation-
of-a-de-bruijn-graph/)

> De Bruijn graphs are widely used in assembly algorithms and I guess writing
your own assembler is a rite of passage. Hoping to get some answers I got this
question from Mick Watson. Since I had a script lying around that I used for
validation I thought I would share it.

**Phylosoft**

@Dr_Bik discussed PhyloSift, which is useful for placing sequences on guide
phylogenetic trees.

[Systematic identification of gene families for use as markers for
phylogenetic and phylogeny- driven ecological studies of bacteria and archaea
and their major subgroups](http://arxiv.org/abs/1307.0869)

> With the astonishing rate that the genomic and metagenomic sequence data
sets are accumulating, there are many reasons to constrain the data analyses.
One approach to such constrained analyses is to focus on select subsets of
gene families that are particularly well suited for the tasks at hand. Such
gene families have generally been referred to as marker genes. We are
particularly interested in identifying and using such marker genes for
phylogenetic and phylogeny-driven ecological studies of microbes and their
communities. We therefore refer to these as PhyEco (for phylogenetic and
phylogenetic ecology) markers. The dual use of these PhyEco markers means that
we needed to develop and apply a set of somewhat novel criteria for
identification of the best candidates for such markers. The criteria we
focused on included universality across the taxa of interest, ability to be
used to produce robust phylogenetic trees that reflect as much as possible the
evolution of the species from which the genes come, and low variation in copy
number across taxa. We describe here an automated protocol for identifying
potential PhyEco markers from a set of complete genome sequences. The protocol
combines rapid searching, clustering and phylogenetic tree building algorithms
to generate protein families that meet the criteria listed above. We report
here the identification of PhyEco markers for different taxonomic levels
including 40 for all bacteria and archaea, 114 for all bacteria, and much more
for some of the individual phyla of bacteria. This new list of PhyEco markers
should allow much more detailed automated phylogenetic and phylogenetic
ecology analyses of these groups than possible previously.

**Nick Loman - CONCOCT**

Nick Loman presented on CONCOCT. Readers can access the paper from following
link.

[CONCOCT: Clustering cONtigs on COverage and
ComposiTion](http://arxiv.org/abs/1312.4038)

> Metagenomics enables the reconstruction of microbial genomes in complex
microbial communities without the need for culturing. Since assembly typically
results in fragmented genomes the grouping of genome fragments (contigs)
belonging to the same genome, a process referred to as binning, remains a
major informatics challenge. Here we present CONCOCT, a computer program that
combines three types of information - sequence composition, coverage across
multiple sample, and read-pair linkage - to automatically bin contigs into
genomes. We demonstrate high recall and precision rates of the program on
artificial as well as real human gut metagenome datasets.

**The Most Profound Advice Given in #UCDAssemble**

If you cannot make things work, send the paper to Nature :)

