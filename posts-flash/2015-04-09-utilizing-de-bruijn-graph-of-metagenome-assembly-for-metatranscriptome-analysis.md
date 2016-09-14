---
title: Utilizing de Bruijn graph of metagenome assembly for metatranscriptome analysis
categories:
- rnaseq
---
Haixu Tang was one of the co-authors of Pevzner's 2001 paper and also
developed the RAPsearch2 program for gene annotation. In this paper, they are
mapping the meta-transcriptome on to the dBG of metagenome.
<!--more-->

[Link](http://arxiv.org/abs/1504.01304)

> Metagenomics research has accelerated the studies of microbial organisms,
providing insights into the composition and potential functionality of various
microbial communities. Metatranscriptomics (studies of the transcripts from a
mixture of microbial species) and other meta-omics approaches hold even
greater promise for providing additional insights into functional and
regulatory characteristics of the microbial communities. Current
metatranscriptomics projects are often carried out without matched metagenomic
datasets (of the same microbial communities). For the projects that produce
both metatranscriptomic and metagenomic datasets, their analyses are often not
integrated. Metagenome assemblies are far from perfect, partially explaining
why metagenome assemblies are not used for the analysis of metatranscriptomic
datasets. Here we report a reads mapping algorithm for mapping of short reads
onto a de Bruijn graph of assemblies. A hash table of junction k-mers (k-mers
spanning branching structures in the de Bruijn graph) is used to facilitate
fast mapping of reads to the graph. We developed an application of this
mapping algorithm: a reference based approach to metatranscriptome assembly
using graphs of metagenome assembly as the reference. Our results show that
this new approach (called TAG) helps to assemble substantially more
transcripts that otherwise would have been missed or truncated because of the
fragmented nature of the reference metagenome. TAG was implemented in C++ and
has been tested extensively on the linux platform. It is available for
download as open source at this http URL

