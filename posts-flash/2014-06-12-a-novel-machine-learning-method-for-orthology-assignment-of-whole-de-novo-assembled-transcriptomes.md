---
title: A Novel Machine Learning Method for Orthology Assignment of Whole de novo Assembled
  Transcriptomes
categories:
- rnaseq
---
A paper titled - [Deep Evolutionary Comparison of Gene Expression Identifies
Parallel Recruitment of Trans-Factors in Two Independent Origins of C4 Photosy
nthesis](http://www.plosgenetics.org/article/info%3Adoi%2F10.1371%2Fjournal.pg
en.1004365) came out in PLOS Genetics. The reason it caught our attention is
the following section. Orthology assignment is a major problem in RNAseq
experiments and the readers may find the method in the paper useful.
<!--more-->

>

To perform comparative analyses of gene expression between C. gynandra and
maize it is necessary to be able to identify homologous genes between the
species in the absence of a reference genome for C. gynandra. This is non-
trivial due to the inherent properties and artefacts of de novo assembled
transcriptomes. For example, it is to be expected that following de novo
assemblies of RNAseq data, most gene loci will be represented by multiple
assembled transcript variants [26][28]. These transcripts may differ from each
other in several ways, for example through single nucleotide polymorphisms,
alternative splicing of internal exons, alternative terminal exons and
incomplete/chimeric assembly due to low sequence coverage or assembly errors.
Homologous transcript identification is further complicated by the large
phylogenetic distance between the species being compared. Increased
phylogenetic distance leads to a concomitant increase in global sequence
divergence between homologous genes in different species. Therefore any method
which is specifically designed for assignment of homologues in de novo
assembled transcriptomes should be able to identify and group multiple
different transcript variants for any given gene to enable comparative
analysis of gene expression.

To determine the suitability of existing assignment methods for identifying
homologous transcript groups in de novo assembled transcriptomes we used
RNAseq data from rice. Here we carried out de novo assembly of the short read
data, and computed an abundance estimate for each de novo assembled
transcript. We also computed an abundance estimate for each gene locus in the
rice reference genome using the same short read data. Several different
strategies for identifying homologous transcripts between the de novo
assembled transcriptome and the rice reference genome were tested and the
accuracy of each strategy was assessed by the global correlation of the
abundance estimates that resulted from the assembled transcripts-to-reference-
gene homology map. Global correlation is negatively affected both by false
positive errors (incorrect homology assignment), false negative errors
(missing orthology assignment) and assembly artefacts (partial and chimeric
transcripts) and so it is a good measure of the utility of an orthology
assignment method for quantitative transcriptome comparisons. When using
simple methods such as a Reciprocal Best-BLAST (RBB) or fixed e-value cut-offs
for assignment abundance estimate accuracies were low and unsuitable for
comparative gene expression analyses (Figure 2A & 2B). Using more complex
methods such as OrthoMCL improved abundance estimate accuracy (Figure 2B).
However accuracy is still low for comparative analyses of gene expression.

The abundance estimate accuracy tests revealed that there was room for
substantial improvement of orthology assignment from de novo assembled
transcriptomes. As there are no specific methods currently available which are
designed to account for the properties and artefacts of de novo assembled
transcriptomes as outlined above, we developed a novel orthology assignment
method to facilitate accurate multispecies comparisons of gene expression from
de novo transcriptome assemblies. The method uses machine learning to define
sequence similarity parameters for gene homologues and thus compensates for
the properties and artefacts of de novo assembled transcriptomes. The first
step in this method is to undertake a pairwise reciprocal best-BLAST (RBB)
analysis (Figure 2C) using the full set of de novo assembled transcripts
against a reference set derived from a reference genome. The RBB hits between
these two datasets are identified (Figure 2D) and grouped according to the
length of the assembled transcript. For each length group the RBB hits are
ranked and the e-value of a chosen percentile is recorded. A matrix of all
e-values and query sequence lengths is then fit to a quadratic polynomial
model by least-squares fitting (Figure 2E). While the RBBs are accepted as
homologues, the function describing this curve is used to classify non-RBB
transcripts of any given length, those above the curve are assigned as
homologues and those below the curve are rejected (Figure 2F). Thus homologue
assignment is conditioned on both the assembled transcript length and also the
global sequence divergence between the de novo assembled and reference
transcriptome. This approach significantly increased the accuracy of abundance
estimates derived from de novo assembled transcripts when compared with
estimates derived from the genome (Figure 2B and 2G). This accuracy is also
robust to large phylogenetic distances. Even when homologous transcripts were
identified using an intermediary reference genome (Arabidopsis thaliana), the
accuracy of mRNA abundance estimates remained high (Figure 2H). We conclude
our assignment method, conditioned on both sequence length and global sequence
divergence, is suitable for comparative analyses of gene expression after de
novo transcript assembly from short read sequencing. For a detailed
description and validation of this method see Text S1. This approach is also
suitable for identifying homologous groups in distantly-related species (see
Text S1 for validation on Oryza sativa versus A. thaliana). Thus we used this
method to enable comparison of gene expression between Cleome gynandra and
maize, an equivalent phylogenetic distance. An online implementation of the
method is provided for use at
www.bioinformatics.plants.ox.ac.uk/annot?ate/index.html.

