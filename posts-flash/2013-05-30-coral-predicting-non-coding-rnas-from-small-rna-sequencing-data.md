---
title: 'CoRAL: Predicting Non-coding RNAs from Small RNA-sequencing Data'
categories:
- ncRNA
---
h/t: @genetics_blog
<!--more-->

[The surprising observation that virtually the entire human genome is
transcribed means we know little about the function of many emerging classes
of RNAs, except their astounding diversities.](http://nar.oxfordjournals.org/c
ontent/early/2013/05/21/nar.gkt426.long)

These guys deserve a kill ENCODE T-shirt from Dan Graur, but otherwise the
paper is useful.

> We first designed algorithms to generate several types of features from
smRNA-seq data based on read length distribution, strand specificity and the
secondary structure of the transcript for transcribed genomic regions. We then
applied a multi-class classification algorithm with feature selection and
cross-validation schemes included to train classifiers among a collection of
known RNA functional classes including lincRNAs, miRNAs, small cytoplasmic RNA
(scRNAs), C/D box snoRNAs, snRNAs and transposon-derived RNAs. For each RNA
class, we identified the most informative features that might be associated
with the molecular mechanisms and metabolic processes of the functional
classes. Trained models, informative features and annotation results have been
validated using (i) external datasets, (ii) SAVoR, a visualization tool for
RNA structures (14), and (iii) curation of the primary literature.

![](http://nar.oxfordjournals.org/content/early/2013/05/21/nar.gkt426/F1.small
.gif)

> The analysis workflow for differentiating between six different classes of
ncRNAs in smRNA-seq data sets.

