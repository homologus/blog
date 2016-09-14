---
title: Alignment-free Comparison of Next-gen Sequences using Compression-based Distance
  Measures
tags: []
categories:
- blog
---
[This newly submitted arxiv paper](http://arxiv.org/abs/1402.0640) (h/t:
@lexnederbragt) is interesting, but we are unable to connect between various
logical flow. The authors first mention that compression-based alignment-free
multiple sequence comparison methods could be better than k-mer based
alignment-free multiple sequence comparison methods.
<!--more-->

> Another class of alignment-free distances arises from information theory, in
particular, from data compression. Those distances are calculated from the
relative information between the input sequences using Kolmogorov complexity
[?, ?, ?], Lempel-Ziv complexity [?]. Unlike k-mer based distance measures
which depend on the parameter k, compression-based distance measures are
parameter-free and hence more consistent.

Then in the final section, it says -

> One possible drawback of the compression-based distance measures is the
running time.  Faster compression tools, especially those developed
speci?cally for NGS short reads such as BEETL [?], SCALCE [?], etc, can be
applied to improve the running time.

When we combine those paragraphs, don't we come a full circle to the
introductory paragraphs of [Jared Simpson's SGA
papers](http://www.homolog.us/blogs/blog/2012/02/11/string-graph-assembler/)?
After all, string graph algorithm could not work for NGS because of enormous
number of pairwise comparisons, and a major contribution of Simpson/Durbin was
to figure out the way to make that manageable.

May be we are missing something, and would like to hear from more
knowledgeable people. The full abstract follows.

![](http://www.spms.ntu.edu.sg/mas/StaffPhoto/Tran%20Ngoc%20Hieu%20-%20photo.j
pg)

> Enormous volumes of short reads data from next-generation sequencing (NGS)
technologies have posed new challenges to the area of genomic sequence
comparison. The multiple sequence alignment approach is hardly applicable to
NGS data due to the challenging problem of short read assembly. Thus
alignment-free methods need to be developed for the comparison of NGS samples
of short reads. Recently, new k-mer based distance measures such as CVTree,
dS^2, co-phylog have been proposed to address this problem. However, those
distances depend considerably on the parameter k, and how to choose the
optimal k is not trivial since it may depend on di?erent aspects of the
sequence data. Hence, in this paper we consider an alternative parameter-free
approach: compression-based distance measures. These measures have shown
impressive performance on long genome sequences in previous studies, but they
have not been tested on NGS short reads. In this study we perform extensive
validation and show that the compression-based distances are highly consistent
with those distances obtained from the k-mer based methods, from the
alignment-based approach, and from existing benchmarks in the literature.
Moreover, as these measures are parameter-free, no optimization is required
and they still perform consistently well on multiple types of sequence data,
for di?erent kinds of species and taxonomy levels. The compression-based
distance measures are assembly-free, alignment-free, parameter-free, and thus
represent useful tools for the comparison of long genome sequences and NGS
samples of short reads.

