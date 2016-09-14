---
title: Kraken - Very Good Application of Jellyfish and Minimizer
tags: []
categories:
- blog
---
A number of good lightweight application are coming out taking advantage of
fast, lock-free kmer counting of Jellyfish. Previously, we discussed about
Sailfish, which could get good speed gain over RSEM in RNAseq applications.
<!--more-->

[DEseq and Sailfish Papers for
RNAseq](http://www.homolog.us/blogs/blog/2013/08/28/deseq-and-sailfish-
papers/)

[Good C++ Development Practices in Sailfish
Code](http://www.homolog.us/blogs/blog/2014/01/21/good-c-development-
practices-sailfish-code/)

We also talked about the Minimer concept published by Jim Yorke in 2004, which
has been finding many uses lately.

[De Novo Assembly of Human Genome with Only 1.5 GB
RAM](http://www.homolog.us/blogs/blog/2014/01/21/de-novo-assembly-human-
genome-1-5-gb-ram/)

Wood and Salzberg published a new paper in Genome Biology for rapidly
classifying metagenome sequences, where they use both of those concepts.

[Kraken: Ultrafast Metagenomic Sequence Classification Using Exact
Alignments](http://genomebiology.com/content/pdf/gb-2014-15-3-r46.pdf)

> Kraken is an ultrafast and highly accurate program for assigning taxonomic
labels to metagenomic DNA sequences. Previous programs designed for this task
have been relatively slow and computationally expensive, forcing researchers
to use faster abundance estimation programs, which only classify small subsets
of metagenomic data. Using exact alignment of k-mers, Kraken achieves
classification accuracy comparable to the fastest BLAST program. In its
fastest mode, Kraken classifies 100 base pair reads at a rate of over 4.1
million reads per minute, 909 times faster than Megablast and 11 times faster
than the abundance estimation program MetaPhlAn. Kraken is available at
http://ccb.jhu.edu/software/kraken/.

Salzberg, as always, continues to do very creative work. Speaking of quality
of Kraken, we are happy to rely on Nick Loman's word on it.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/03/Capture5-300x48.png)

