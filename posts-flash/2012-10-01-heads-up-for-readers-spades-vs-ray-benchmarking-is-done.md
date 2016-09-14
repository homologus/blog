---
title: Heads Up for Readers - SPAdes vs Ray Benchmarking is Done
tags: []
categories:
- blog
---
Few days back, Sbastien Boisvert, the author of highly efficient Ray
assembler, [commented](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-
graphs-to-rectangle-graphs-for-genome-assembly/) on relative performance of
Ray vs SPAdes assemblers (also read
[here](http://www.homolog.us/blogs/2012/09/20/a-comment-from-developer-of-ray-
assembler/)). The SPAdes group completed their comparison and updated [the
benchmarking table on their
website](http://quast.bioinf.spbau.ru/benchmarking). Alexey Gurevich of SPAdes
team was kind enough to explain their observations in the comment section of
an [earlier rectangular graph-related
commentary](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-graphs-to-
rectangle-graphs-for-genome-assembly/). We request readers to post additional
comments under the [same thread](http://www.homolog.us/blogs/2012/09/12/from-
de-bruijn-graphs-to-rectangle-graphs-for-genome-assembly/) so that they all
stay at the same place and can be easily followed.
<!--more-->

Readers are warned that the above exchanges are not meant to declare one
single winner among all assemblers. Genome assembly has always been a
difficult problem, and has only gotten more complex with arrival of short
reads. Each team writing a new assembly program tries to optimize between
several factors -

(i) **type of nucleotide data** \- small genome, large repeat-prone genome,
highly polymorphic genome, single cell, metagenome, transcriptome, etc.

(ii) **type of sequencing technology** \- read length, read quality, paired
ends, pairing distances, etc.

(iii) **type of computer hardware** \- single CPU, multicore, computer
cluster, Condor, GPU, Hadoop, amount of available RAM, etc.

With so many factors in play and with each genome assembly team learning from
each other, it may be better to understand at a simple level how each
assembler does and what problem it was most optimized to address that hoping
to find one magic bullet. The challenges are no different in sequence
alignment space, where arrival of Bowtie did not make BLAST obsolete, because
two alignment programs excel in solving two different kind of problems.

