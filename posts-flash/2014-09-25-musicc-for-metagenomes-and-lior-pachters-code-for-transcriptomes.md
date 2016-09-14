---
title: MUSiCC for Metagenomes and Lior Pachter's Code for Transcriptomes
tags: []
categories:
- blog
---
Lior Pachter is having a discussion on the mathematical aspects of digital
normalization ([Digital normalization
revealed](http://liorpachter.wordpress.com/2014/09/11/digital-normalization-
revealed/#comment-2356)). This is related to his work with David Tse's group
and we posted the relevant tutorial slides
[here](http://www.homolog.us/blogs/blog/2014/09/09/tutorial-on-david-tses-
work-on-dnarna-assembly-presented-at-isit-2014/). Pachter and his student
Sreeram are developing a code to analyze de novo assembled RNAseq data.
<!--more-->

In the context of doing similar mathematical analysis for metagenomes, the
readers may find the following paper useful.

[Link](http://biorxiv.org/content/early/2014/09/19/009407)

> Functional metagenomic analyses commonly involve a normalization step, where
measured levels of genes or pathways are converted into relative abundances.
Here, we demonstrate that this normalization scheme introduces marked biases
both across and within human microbiome samples and systematically identify
various sample- and gene-specific properties that contribute to these biases.
We introduce an alternative normalization paradigm, MUSiCC, which combines
universal single-copy genes with machine learning methods to correct these
biases and to obtain a more accurate and biologically meaningful measure of
gene abundances. Finally, we demonstrate that MUSiCC significantly improves
downstream discovery of functional shifts in the microbiome. MUSiCC is
available at http://elbo.gs.washington.edu/software.html.

