---
title: A comparison of Methods for Differential Expression Analysis of RNA-seq Data
tags: []
categories:
- rnaseq
---
Few days back, [we posted a large
table](http://www.homolog.us/blogs/2013/03/13/methods-to-study-eventisoform-
expression-and-alternative-splicing-from-rna-seq/) with list of various RNAseq
analysis programs. Before we got a chance to go through the programs to see
how well they work, [another interesting paper came
out](http://www.biomedcentral.com/1471-2105/14/91/abstract) claiming to do the
same.
<!--more-->

>

**Results**

We conducted an extensive comparison of eleven methods for differential
expression analysis of RNA-seq data. All methods are freely available within
the R framework and take as input a matrix of counts, i.e. the number of reads
mapping to each genomic feature of interest in each of a number of samples. We
evaluate the methods based on both simulated data and real RNA-seq data.

**Conclusions**

Very small sample sizes, which are still common in RNA-seq experiments, impose
problems for all evaluated methods and any results obtained under such
conditions should be interpreted with caution. For larger sample sizes, the
methods combining a variance-stabilizing transformation with the 'limma'
method for differential expression analysis perform well under many different
conditions, as does the nonparametric SAMseq method.

Please note that above paper only compares the differential expression aspect,
whereas the earlier table also included tools for finding alternatively
spliced genes, de novo transcriptome assembly, etc.

