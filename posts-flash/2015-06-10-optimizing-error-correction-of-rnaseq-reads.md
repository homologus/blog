---
title: Optimizing error correction of RNAseq reads
categories:
- rnaseq
---
[Link](http://biorxiv.org/content/early/2015/05/29/020123)
<!--more-->

> Motivation: The correction of sequencing errors contained in Illumina reads
derived from genomic DNA is a common pre-processing step in many de novo
genome assembly pipelines, and has been shown to improved the quality of
resultant assemblies. In contrast, the correction of errors in transcriptome
sequence data is much less common, but can potentially yield similar
improvements in mapping and assembly quality. This manuscript evaluates
several popular read-correction tool's ability to correct sequence errors
commonplace to transcriptome derived Illumina reads. Results: I evaluated the
efficacy of correction of transcriptome derived sequencing reads using using
several metrics across a variety of sequencing depths. This evaluation
demonstrates a complex relationship between the quality of the correction,
depth of sequencing, and hardware availability which results in variable
recommendations depending on the goals of the experiment, tolerance for false
positives, and depth of coverage. Overall, read error correction is an
important step in read quality control, and should become a standard part of
analytical pipelines. Availability: Results are non-deterministically
repeatable using AMI:ami-3dae4956 (MacManes EC 2015) and the Makefile
available here: https://goo.gl/oVIuE0

