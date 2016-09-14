---
title: Joe Pickrell 'Publishes' Henrietta Lacks&rsquo;s Genome from Public Data
tags: []
categories:
- blog
---
In his 'genomes unzipped' blog, Joe Pickrell provides another perspective on
the idiotic politicization surrounding HeLa genome sequencing. He explains
that if the reference human genome is publicly available, and if the
difference between reference human genome and HeLa line is publicly available
based on RNAseq, ChIP-seq and many other large-scale comparative study, any
bioinformatician with half-a-brain can reconstruct the genome sequence of
Henrietta Lacks. For those who cannot, his blog gave 'materials and methods'
section explaining how to.
<!--more-->

>

Technical details:

I downloaded sequencing data from the following GEO accessions: SRR227441,
SRR227442, SRR227445, SRR227446, SRR227472, SRR227473, SRR227505, SRR227506,
SRR227556, SRR227557, SRR350914, SRR350915 SRR568260, SRR568261, SRR577378,
SRR577379, SRR577392, SRR577393, SRR577429, SRR577430

These are all ChIP-seq experiments on HeLa cells from the ENCODE project.

I then mapped reads to human hg19 using bwa. To compare to the 1000 Genomes
data, I used the genotypes from the Illumina OMNI array. To merge HeLa into
these data, I randomly sampled a single sequencing read covering each site on
the array (at all sites that had at least a single read covering it) and
reported the sequence from that read as the HeLa genotype (calling
heterozygotes is moderately annoying, so I didnt try it). In total I genotyped
2095422/2177885 (96%) of sites successfully with this approach. I then ran PCA
(using smartpca) on the genotypes from the YRI, ASW, CEU, CHB, and HeLa
samples.

