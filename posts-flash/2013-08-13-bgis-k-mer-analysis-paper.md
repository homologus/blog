---
title: BGI's K-mer Analysis Paper
tags: []
categories:
- blog
---
They always come in three, don't they? We covered [Rayan Chikhi's
KmerGenie](http://www.homolog.us/blogs/blog/2013/04/23/informed-and-
automated-k-mer-size-selection-for-genome-assembly/) (also see
[here](http://www.homolog.us/blogs/blog/2013/07/22/rayan-chikhis-kmergenie-
slides-from-hitseq-2013/)) and Jared Simpson's [assembly preprocessing
module](http://www.homolog.us/blogs/blog/2013/07/02/cool-preprocessing-model-
for-genome-assembly/) (also check
[here](http://www.homolog.us/blogs/blog/2013/07/31/exploring-genome-
characteristics-and-sequence-quality-without-a-reference/)).
<!--more-->

Now BGI submitted their paper along the same line to
[arxiv](http://arxiv.org/ftp/arxiv/papers/1308/1308.2012.pdf). (h/t:
@lexnederberg)

> Background: With the fast development of next generation sequencing
technologies, increasing numbers of genomes are being de novo sequenced and
assembled. However, most are in fragmental and incomplete draft status, and
thus it is often difficult to know the accurate genome size and repeat
content. Furthermore, many genomes are highly repetitive or heterozygous,
posing problems to current assemblers utilizing short reads. Therefore, it is
necessary to develop efficient assembly-independent methods for accurate
estimation of these genomic characteristics.

Results: Here we present a framework for modeling the distribution of k-mer
frequency from sequencing data and estimating the genomic characteristics such
as genome size, repeat structure and heterozygous rate. By introducing novel
techniques of k-mer individuals, float precision estimation, and proper
treatment of sequencing error and coverage bias, the estimation accuracy of
our method is significantly improved over existing methods. We also studied
how the various genomic and sequencing characteristics affect the estimation
accuracy using simulated sequencing data, and discussed the limitations on
applying our method to real sequencing data. Conclusion: Based on this
research, we show that the k-mer frequency analysis can be used as a general
and assembly-independent method for estimating genomic characteristics, which
can improve our understanding of a species genome, help design the sequencing
strategy of genome projects, and guide the development of assembly algorithms.
The programs developed in this research are written using C/C++ and freely
accessible at [this ftp URL.](ftp://ftp.genomics.org.cn/pub/gce.)

On k-mer counting, we covered four important papers at this link -

[Quip, Minia, SlimGene and Titus Browns paper on Scaling
Metagenome](http://www.homolog.us/blogs/blog/2012/07/19/quip-minia-slimgene-
and-titus-browns-paper-on-scaling-metagenome/)

