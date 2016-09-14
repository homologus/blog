---
title: Centrifuge - A Low RAM Metagenomic Classifier from Salzberg Group
tags: []
categories:
- blog
---
Apart from metagenome classifiers like
[NBC](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3008645/) and
[LMAT](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3753567/) published in
2011-2013, our readers came across a number of newly published metagenomic
classifiers in recent months. Those include
[Kraken](http://www.homolog.us/blogs/blog/2014/03/07/kraken-good-application-
jellyfish-minimizer/), [Clark](http://www.biomedcentral.com/1471-2164/16/236),
[Kallisto](http://www.homolog.us/blogs/blog/2015/10/27/the-march-of-
pseudoalignment-two-papers/) and the very recent [Kaiju from Anders Krogh's
group](http://www.homolog.us/blogs/blog/2015/12/03/kaiju-fast-and-sensitive-
taxonomic-classification-for-metagenomics/). They may like another one that is
being actively developed (h/t: @StevenSalzberg1). From its [github
page](https://github.com/infphilo/centrifuge) \-
<!--more-->

> Centrifuge is a very rapid and memory-efficient system for the
classification of DNA sequences from microbial samples, with better
sensitivity than and comparable accuracy to other leading systems. The system
uses a novel indexing scheme based on the Burrows-Wheeler transform (BWT) and
the Ferragina-Manzini (FM) index, optimized specifically for the metagenomic
classification problem. Centrifuge requires a relatively small index (e.g.,
2.9 GB for ~2,800 bacterial genomes) yet provides very fast classification
speed, allowing it to process a typical DNA sequencing run within an hour.
Together these advances enable timely and accurate analysis of large
metagenomics data sets on conventional desktop computers.

The novelty of this work is in coming up with a BTW scheme that compresses the
microbial genomes within a low memory footprint. You can learn more
[here](http://www.ccb.jhu.edu/people/infphilo/data/Centrifuge-poster.pdf).

