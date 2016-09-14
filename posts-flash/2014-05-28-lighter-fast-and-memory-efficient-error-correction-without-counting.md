---
title: 'Lighter: fast and memory-efficient error correction without counting'
tags: []
categories:
- blog
---
Kmer counting is usually the first step in analysis of NGS sequences. In [Kmer
Counting a 2014 Recap](http://www.homolog.us/blogs/blog/2014/04/07/kmer-
counting-a-2014-recap/), we brought the topic of kmer counting up to date. To
further speed up execution, some researchers are designing algorithms to skip
the k-mer counting step altogether, as you can see in [this
paper](http://biorxiv.org/content/early/2014/05/27/005579).
<!--more-->

> Lighter is a fast and memory-efficient tool for correcting sequencing errors
in high-throughput sequencing datasets. Lighter avoids counting k-mers in the
sequencing reads. Instead, it uses a pair of Bloom filters, one populated with
a sample of the input k-mers and the other populated with k-mers likely to be
correct based on a simple test. As long as the sampling fraction is adjusted
in inverse proportion to the depth of sequencing, the Bloom filter size can be
held constant while maintaining near-constant accuracy. Lighter is easily
applied to very large sequencing datasets. It is parallelized, uses no
secondary storage, and is both faster and more memory-efficient than competing
approaches while achieving comparable accuracy. Lighter is free open source
software available from https://github.com/mourisl/Lighter/.

