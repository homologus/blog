---
title: Influence of RNA Extraction Methods and Library Selection Schemes on RNA-seq
  Data
categories:
- rnaseq
---
We came across [this BMC Genomics
paper](http://www.biomedcentral.com/1471-2164/15/675/abstract) in twitter, but
did not get time to read yet. Hopefully, the readers will find it useful.
<!--more-->

>

**Background**

Gene expression analysis by RNA sequencing is now widely used in a number of
applications surveying the whole transcriptomes of cells and tissues. The
recent introduction of ribosomal RNA depletion protocols, such as RiboZero,
has extended the view of the polyadenylated transcriptome to the poly (A)-
fraction of the RNA. However, substantial amounts of intronic transcriptional
activity has been reported in RiboZero protocols, raising issues regarding
their potential nuclear origin and the impact on the actual sequence depth in
exonic regions.

**Results**

Using HEK293 human cells as source material, we assessed here the impact of
the two commonly used RNA extraction methods and of the library construction
protocols (rRNA depletion versus mRNA) on 1) the relative abundance of
intronic reads and 2) on the estimation of gene expression values. We
benchmarked the rRNA depletion-based sequencing with a specific analysis of
the cytoplasmic and nuclear transcriptome fractions, suggesting that the large
majority of the intronic reads correspond to unprocessed nuclear transcripts
rather than to independent transcriptional units. We show that Qiagen or
TRIzol extraction methods retain differentially nuclear RNA species, and that
consequently, rRNA depletion-based RNA sequencing protocols are particularly
sensitive to the extraction methods.

**Conclusions**

We could show that the combination of Trizol-based RNA extraction with rRNA
depletion sequencing protocols led to the largest fraction of intronic reads,
after the sequencing of the nuclear transcriptome. We discuss here the impact
of the various strategies on gene expression and alternative splicing
estimation measures. Further, we propose guidelines and a double selection
strategy for minimizing the expression biases, without loss of information.

