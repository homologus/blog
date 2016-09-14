---
title: 'BALSA: Integrated secondary analysis for whole-genome and whole-exome sequencing,
  accelerated by GPU'
tags: []
categories:
- blog
---
A new bioinformatics paper from Ruibang Luo? and others in Tak-Wah Lam's
group.
<!--more-->

[BALSA: Integrated secondary analysis for whole-genome and whole-exome
sequencing, accelerated by GPU](https://peerj.com/preprints/373/)

> This paper reports an integrated solution, called BALSA, for the secondary
analysis of next generation sequencing data; it exploits the computational
power of GPU and an intricate memory management to give a fast and accurate
analysis. From raw reads to variants (including SNPs and Indels), BALSA, using
just a single computing node with a commodity GPU board, takes 5.5 hours to
process 50-fold whole genome sequencing (~750 million 100bp paired-end reads),
or just 25 minutes for 210-fold whole exome sequencing. BALSAs speed is rooted
at its parallel algorithms to effectively exploit a GPU to speed up processes
like alignment, realignment and statistical testing. BALSA incorporates a
16-genotype model to support the calling of SNPs and Indels and achieves
competitive variant calling accuracy and sensitivity when compared to the
ensemble of six popular variant callers. BALSA also supports efficient
identification of somatic SNVs and CNVs; experiments showed that BALSA
recovers all the previously validated somatic SNVs and CNVs, and it is more
sensitive for somatic Indel detection. BALSA outputs variants in VCF format. A
pileup-like SNAPSHOT format, while maintaining the same fidelity as BAM in
variant calling, enables efficient storage and indexing, and facilitates the
App development of downstream analyses.

For previous work from the same group, please check -

[GPU-Accelerated BWT Construction for Large Collection of Short
Reads](http://www.homolog.us/blogs/blog/2014/01/29/gpu-accelerated-bwt-
construction-large-collection-short-reads/)

[SOAP3-dp: Fast, Accurate and Sensitive GPU-Based Short Read
Aligner](http://www.homolog.us/blogs/blog/2013/06/07/soap3-dp-fast-accurate-
and-sensitive-gpu-based-short-read-aligner/)

\---------------------------------------------------

We just finished reading the paper and found the benchmarks quite impressive.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/04/Capture27-300x105.png)

> In summary, from raw reads to variants (including SNPs and Indels), BALSA
finished in 5.49 hours, whereas ISAAC finished in 11.92 hours, and GATK
coupled with BWAaln, BWAmem and SOAP3-?dp in 88.00, 48.68 and 46.27 hours,
respectively.

They claimed that this performance gain did not come at the cost of quality.

> BALSA (and SOAP3-?dp) has the highest alignment sensitivity. When measuring
the number of read pairs that have both ends aligned and paired,
SOAP3-?dp/BALSA reports 97.08%, BWAmem 95.74%, BWAaln 92.22% and ISAAC 91.42%
(see table S1 for details).

