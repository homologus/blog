---
title: Reference-free detection of isolated SNPs
tags: []
categories:
- blog
---
Another [de Bruijn graph magic](http://nar.oxfordjournals.org/content/early/20
14/11/16/nar.gku1187.full) by Raluca Uricaru, Rayan Chikhi, Guillaume Rizk and
co-authors.
<!--more-->

> Detecting single nucleotide polymorphisms (SNPs) between genomes is becoming
a routine task with next-generation sequencing. Generally, SNP detection
methods use a reference genome. As non-model organisms are increasingly
investigated, the need for reference-free methods has been amplified. Most of
the existing reference-free methods have fundamental limitations: they can
only call SNPs between exactly two datasets, and/or they require a prohibitive
amount of computational resources. The method we propose, DISCOSNP, detects
both heterozygous and homozygous isolated SNPs from any number of read
datasets, without a reference genome, and with very low memory and time
footprints (billions of reads can be analyzed with a standard desktop
computer). To facilitate downstream genotyping analyses, DISCOSNP ranks
predictions and outputs quality and coverage per allele. Compared to finding
isolated SNPs using a state-of-the-art assembly and mapping approach, DISCOSNP
requires significantly less computational resources, shows similar
precision/recall values, and highly ranked predictions are less likely to be
false positives. An experimental validation was conducted on an arthropod
species (the tick Ixodes ricinus) on which de novo sequencing was performed.
Among the predicted SNPs that were tested, 96% were successfully genotyped and
truly exhibited polymorphism.

