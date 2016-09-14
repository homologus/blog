---
title: 'Rail-RNA: Scalable analysis of RNA-seq splicing and coverage'
categories:
- rnaseq
---
[Link](http://biorxiv.org/content/early/2015/05/07/019067)
<!--more-->

> RNA sequencing (RNA-seq) experiments now span hundreds to thousands of
samples. A source of frustration for investigators analyzing a given dataset
is the inability to rapidly and reproducibly align its samples jointly.
Current spliced alignment software is designed to analyze each sample
separately. Consequently, no information is gained from analyzing multiple
samples together, and it is difficult to reproduce the exact analysis without
access to original computing resources. We describe Rail-RNA, a cloud-enabled
spliced aligner that analyzes many samples at once. Rail-RNA eliminates
redundant work across samples, making it more efficient as samples are added.
For many samples, Rail-RNA is more accurate than annotation-assisted aligners.
We use Rail-RNA to align 666 RNA-seq samples from the GEUVADIS project on
Amazon Web Services in 12 hours for US$0.69 per sample. Rail-RNA produces
alignments and base-resolution bigWig coverage files, ready for use with
downstream packages for reproducible statistical analysis. We identify 290,416
expressed regions in the GEUVADIS samples, including 21,224 that map to
intergenic sequence. We show that these regions show consistent patterns of
variation across populations and with respect to known technological
confounders. We identify expressed regions in the GEUVADIS samples and show
that both annotated and unannotated (novel) expressed regions exhibit
consistent patterns of variation across populations and with respect to known
confounders. Rail-RNA is open-source software available at http://rail.bio .

