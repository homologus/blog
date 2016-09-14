---
title: 'Kaiju: Fast and sensitive taxonomic classification for metagenomics'
tags: []
categories:
- blog
---
After Kraken, Clark, Kallisto and LMAT, here is another metagenomic
classifier. The authors are using MEM and BWT.
<!--more-->

[Link](http://biorxiv.org/content/early/2015/11/16/031229)

> The constantly decreasing cost and increasing output of current sequencing
technologies enable large scale metagenomic studies of microbial communities
from diverse habitats. Therefore, fast and accurate methods for taxonomic
classification are needed, which can operate on increasingly larger datasets
and reference databases. Recently, several fast metagenomic classifiers have
been developed, which are based on comparison of genomic k-mers. However,
nucleotide comparison using a fixed k-mer length often lacks the sensitivity
to overcome the evolutionary distance between sampled species and genomes in
the reference database. Here, we present the novel metagenome classifier Kaiju
for fast assignment of reads to taxa. Kaiju finds maximum exact matches on the
protein-level using the Borrows-Wheeler transform, and can optionally allow
amino acid substitutions in the search using a greedy heuristic. We show in a
genome exclusion study that Kaiju can classify more reads with higher
sensitivity and similar precision compared to fast k-mer based classifiers,
especially in genera that are underrepresented in reference databases. We also
demonstrate that Kaiju classifies more than twice as many reads in ten real
metagenomes compared to programs based on genomic k-mers. Kaiju can process up
to millions of reads per minute, and its memory footprint is below 5 GB of
RAM, allowing the analysis on a standard PC. The program is available under
the GPL3 license at: github.com/bioinformatics-centre/kaiju

