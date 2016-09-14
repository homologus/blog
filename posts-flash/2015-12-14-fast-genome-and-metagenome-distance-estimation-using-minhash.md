---
title: Fast genome and metagenome distance estimation using MinHash
tags: []
categories:
- blog
---
[Link](http://biorxiv.org/content/early/2015/10/26/029827)
<!--more-->

> Given a massive collection of sequences, it is infeasible to perform
pairwise alignment for basic tasks like sequence clustering and search. To
address this problem, we demonstrate that the MinHash technique, first applied
to clustering web pages, can be applied to biological sequences with similar
effect, and extend this idea to include biologically relevant distance and
significance measures. Our new tool, Mash, uses MinHash locality-sensitive
hashing to reduce large sequences to a representative sketch and rapidly
estimate pairwise distances between genomes or metagenomes. Using Mash, we
explored several use cases, including a 5,000-fold size reduction and
clustering of all ~55,000 NCBI RefSeq genomes in 46 CPU hours. The resulting
93 MB sketch database includes all RefSeq genomes, effectively delineates
known species boundaries, reconstructs approximate phylogenies, and can be
searched in seconds using assembled genomes or raw sequencing runs from
Illumina, Pacific Biosciences, and Oxford Nanopore. For metagenomics, Mash
scales to thousands of samples and can replicate Human Microbiome Project and
Global Ocean Survey results in a fraction of the time. Other potential
applications include any problem where an approximate, global sequence
distance is acceptable, e.g. to triage and cluster sequence data, assign
species labels to unknown genomes, quickly identify mis-tracked samples, and
search massive genomic databases. In addition, the Mash distance metric is
based on simple set intersections, which are compatible with homomorphic
encryption schemes. To facilitate integration with other software, Mash is
implemented as a lightweight C++ toolkit and freely released under a BSD
license at https://github.com/marbl/mash.

