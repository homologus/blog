---
title: Chimeras and Fusion Transcripts in RNAseq Assembly
categories:
- rnaseq
---
We came across this paper from 2013 that is helpful for those working on
RNAseq assembly. (h/t: Richard Smith)
<!--more-->

[Optimizing de novo assembly of short-read RNA-seq data for
phylogenomics](http://www.biomedcentral.com/1471-2164/14/328)

> Background

RNA-seq has shown huge potential for phylogenomic inferences in non-model
organisms. However, error, incompleteness, and redundant assembled transcripts
for each gene in de novo assembly of short reads cause noise in analyses and a
large amount of missing data in the aligned matrix. To address these problems,
we compare de novo assemblies of paired end 90 bp RNA-seq reads using Oases,
Trinity, Trans-ABySS and SOAPdenovo-Trans to transcripts from genome
annotation of the model plant Ricinus communis. By doing so we evaluate
strategies for optimizing total gene coverage and minimizing assembly chimeras
and redundancy.

Results

We found that the frequency and structure of chimeras vary dramatically among
different software packages. The differences were largely due to the number of
trans-self chimeras that contain repeats in the opposite direction. More than
half of the total chimeras in Oases and Trinity were trans-self chimeras.
Within each package, we found a trade-off between maximizing reference
coverage and minimizing redundancy and chimera rate. In order to reduce
redundancy, we investigated three methods: 1) using cap3 and CD-HIT-EST to
combine highly similar transcripts, 2) only retaining the transcript with the
highest read coverage, or removing the transcript with the lowest read
coverage for each subcomponent in Trinity, and 3) filtering Oases single k-mer
assemblies by number of transcripts per locus and relative transcript length,
and then finding the transcript with the highest read coverage. We then
utilized results from blastx against model protein sequences to effectively
remove trans chimeras. After optimization, seven assembly strategies among all
four packages successfully assembled 42.947.1% of reference genes to more than
200 bp, with a chimera rate of 0.922.21%, and on average 1.83.1 transcripts
per reference gene assembled.

Conclusions

With rapidly improving sequencing and assembly tools, our study provides a
framework to benchmark and optimize performance before choosing tools or
parameter combinations for analyzing short-read RNA-seq data. Our study
demonstrates that choice of assembly package, k-mer sizes, post-assembly
redundancy-reduction and chimera cleanup, and strand-specific RNA-seq library
preparation and assembly dramatically improves gene coverage by non-redundant
and non-chimeric transcripts that are optimized for downstream phylogenomic
analyses.

