---
title: Characterizing and Measuring Bias in Sequence Data
tags: []
categories:
- blog
---
Bias and artifact papers are very uncool and we do not think press will be
calling David Jaffe and his colleagues to know whether they changed biology
textbooks. However, we like covering them, because their newly published
[Genome Biology paper](http://genomebiology.com/2013/14/5/R51/abstract) will
be very useful for those fighting in the trenches. To know how sequencing bias
impacts de Bruijn graphs and next-gen assembly, also check C. Titus Brown's
paper covered in our prior commentary - [Illumina Sequencing Artifacts
Revealed by Connectivity Analysis of Metagenomic
Datasets](http://www.homolog.us/blogs/blog/2013/01/21/illumina-sequencing-
artifacts-revealed-by-connectivity-analysis-of-metagenomic-datasets/).
<!--more-->

The abstract of paper from Broad Institute follows:

>

**Background**

DNA sequencing technologies deviate from the ideal uniform distribution of
reads. These biases impair scientific and medical applications. Accordingly,
we have developed computational methods for discovering, describing and
measuring bias.

**Results**

We applied these methods to the Illumina, Ion Torrent, Pacific Biosciences and
Complete Genomics sequencing platforms, using data from human and from a set
of microbes with diverse base compositions. As in previous work, library
construction conditions significantly influence sequencing bias. Pacific
Biosciences coverage levels are the least biased, followed by Illumina,
although all technologies exhibit error-rate biases in high- and low-GC
regions and at long homopolymer runs. The GC-rich regions prone to low
coverage include a number of human promoters, so we therefore catalog 1,000
that were exceptionally resistant to sequencing. Our results indicate that
combining data from two technologies can reduce coverage bias if the biases in
the component technologies are complementary and of similar magnitude.
Analysis of Illumina data representing 120-fold coverage of a well-studied
human sample reveals that 0.20% of the autosomal genome was covered at less
than 10% of the genome-wide average. Excluding locations that were similar to
known bias motifs or likely due to sample-reference variations left only
0.045% of the autosomal genome with unexplained poor coverage.

**Conclusions**

The assays presented in this paper provide a comprehensive view of sequencing
bias, which can be used to drive laboratory improvements and to monitor
production processes. Development guided by these assays should result in
improved genome assemblies and better coverage of biologically important loci.

