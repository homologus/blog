---
title: 'rHAT: fast alignment of noisy long reads with regional hashing.'
tags: []
categories:
- blog
---
[Link](http://www.ncbi.nlm.nih.gov/pubmed/26568628)
<!--more-->

> MOTIVATION:

Single Molecule Real-Time (SMRT) sequencing has been widely applied in
cutting-edge genomic studies. However, it is still an expensive task to align
the noisy long SMRT reads to reference genome by state-of-the-art aligners,
which is becoming a bottleneck in applications with SMRT sequencing. Novel
approach is on demand for improving the efficiency and effectiveness of SMRT
read alignment.

RESULTS:

We propose Regional Hashing-based Alignment Tool (rHAT), a seed-and-extension-
based read alignment approach specifically designed for noisy long reads. rHAT
indexes reference genome by regional hash table (RHT), a hash table-based
index which describes the short tokens within local windows of reference
genome. In the seeding phase, rHAT utilizes RHT for efficiently calculating
the occurrences of short token matches between partial read and local genomic
windows to find highly possible candidate sites. In the extension phase, a
sparse dynamic programming-based heuristic approach is used for reducing the
cost of aligning read to the candidate sites. By benchmarking on the real and
simulated datasets from various prokaryote and eukaryote genomes, we
demonstrated that rHAT can effectively align SMRT reads with outstanding
throughput.

AVAILABILITY AND IMPLEMENTATION:

rHAT is implemented in C++; the source code is available at https://github.com
/HIT-Bioinformatics/rHAT.

