---
title: Indexing Arbitrary-length K-mers in Sequencing Reads
tags: []
categories:
- blog
---
Today's must read paper is [this one](http://arxiv.org/pdf/1502.01861v1.pdf)
from the KMC group, who has done amazing work using minimizers. (h/t: Rob
Patro) We also seem to have missed their other paper that seems quite
interesting - [Grabowski S, Raniszewski M (2014). Sampling the suffix array
with minimizers. Publicly available preprint arXiv:1406.2348v2].
<!--more-->

> We propose a lightweight data structure for indexing and querying
collections of NGS reads data in main memory. The data structure supports the
interface proposed in the pioneering work by Philippe et al. for counting and
locating k-mers in sequencing reads. Our solution, PgSA (pseudogenome suffix
array), based on finding overlapping reads, is competitive to the existing
algorithms in the space use, query times, or both. The main applications of
our index include variant calling, error correction and analysis of reads from
RNA-seq experiments.

