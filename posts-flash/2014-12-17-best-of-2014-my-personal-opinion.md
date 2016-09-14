---
title: "'Best of 2014' - My Personal Opinion"
tags: []
categories:
- blog
---
Last year, I assembled a panel of judges, who chose the best bioinformatics
contributions of the year from a number of suggestions made by the readers.
You can see the results in [Announcing the Results of Best of
2013?](http://www.homolog.us/blogs/blog/2014/01/20/announcing-results-
best-2013/).
<!--more-->

The entire process took quite a bit of time of everyone involved. Moreover, we
had an early start to make the effort visible and get the most feedback from
readers. This year I got busy and did not find enough time to notify the
judges and the readers. So, instead of having the 'Best of 2014' in the same
way as last year, I will share the ideas I found most interesting and
encourage you to do the same in comment section.

**1\. Succint de Bruijn Graph**

[Variable-Order de Bruijn Graphs](http://arxiv.org/abs/1411.2718)

[MEGAHIT: An ultra-fast single-node solution for large and complex
metagenomics assembly via succinct de Bruijn
graph](http://arxiv.org/abs/1409.7208)

Very recently, two papers came out implementing the succint de Bruijn graph
idea of Alex Bowe et al. I found both of them quite interesting. The idea of
succint de Bruijn graph merges two concepts - (i) de Bruijn graphs for
assembly, (ii) XBW transform for graphs with its associated rank and select
structure. The paper on variable order de Bruijn graph showed how succint de
Bruijn graph could be used to naturally progress to de Bruijn graphs of
multiple kmer sizes and I found that quite elegant.

**2\. Minimizer**

[On the representation of de Bruijn Graph](http://arxiv.org/abs/1401.5383)

[KMC 2: Fast and resource-frugal k-mer
counting](http://arxiv.org/abs/1407.1507)

Chikhi et al's merger of assembly and minimizer was quite elegant. The aspects
of KMC2 paper I found most interesting were - (i) treatment of homopolymer
minimizers to adjust bucket sizes, (ii) highly parallel code.

**3\. Cache-efficient common kmer finding in DALIGNER**

[DALIGNER: Fast and sensitive detection of all pairwise local
alignments](https://dazzlerblog.wordpress.com/2014/07/10/dalign-fast-and-
sensitive-detection-of-all-pairwise-local-alignments/)

In DALIGNER paper, Gene Myers came up with a cache-efficient method for
finding common k-mers from two reads, and the method scaled almost linearly
with the number of cores. I found that quite elegant. Also, his method to use
Pacbio stats to cut down unlikely paths in O(ND) alignment to make it useful
for long reads was very good.

\------------------------------------

The above is only a subset of a large number of unusual contributions made by
bioinformatics researchers. A bigger list of interesting papers on NGS can be
found in [ASHG/GA4GH Special A Recap of Interesting NGS Algorithms of the
Year](http://www.homolog.us/blogs/blog/2014/10/18/ashg-special-a-recap-of-
interesting-ngs-algorithms-of-the-year/). Please share in comment section any
idea, paper, blog or teaching tool that you enjoyed.

