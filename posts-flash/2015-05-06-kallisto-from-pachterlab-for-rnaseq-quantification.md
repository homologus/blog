---
title: Kallisto from Pachterlab for RNAseq Quantification
categories:
- rnaseq
---
We already posted slides on this topic a few months back. Now the code and
other details are available online from Pachter's website.
<!--more-->

[Link](http://pachterlab.github.io/kallisto/about.html)

> kallisto is a program for quantifying abundances of transcripts from RNA-Seq
data, or more generally of target sequences using high-throughput sequencing
reads. It is based on the novel idea of pseudoalignment for rapidly
determining the compatibility of reads with targets, without the need for
alignment. On benchmarks with standard RNA-Seq data, kallisto can quantify 30
million human reads in less than 3 minutes on a Mac desktop computer using
only the read sequences and a transcriptome index that itself takes less than
10 minutes to build. Pseudoalignment of reads preserves the key information
needed for quantification, and kallisto is therefore not only fast, but also
as accurate than existing quantification tools. In fact, because the
pseudoalignment procedure is robust to errors in the reads, in many benchmarks
kallisto significantly outperforms existing tools.

The figures above show the performance of kallisto as compared to other
programs. Running times are based on 20 cores used to quantify 20 samples each
with 30 million reads. kallisto is hundreds of times faster than standard
tools (when disk access is not a limiting factor kallisto is even faster,
averaging about 2.5 minutes per run). Sailfish is much faster than most tools,
although still significantly slower than kallisto, and its approach of
shredding reads into k-mers reduces accuracy. This can be seen in the plot on
the right which shows the median relative difference of quantifications with
respect to the truth from simulations. Reads were simulated using the RSEM
simulator.

The speed of kallisto makes it tractable to use the bootstrap to determine
uncertainty on estimates. Uncertainty estimates can be used in downstream
applications and kallisto includes infrastructure for managing the large
amount of data associated with bootstrapped samples. A companion tool to
kallisto, called sleuth can be used to visualize and interpret kallisto
quantifications, and soon to perform many popular differential analyses in a
way that accounts for uncertainty in estimates.

