---
title: Minimap - A Minimizer-based Mapping Program
tags: []
categories:
- blog
---
Heng Li released a [blazing fast mapping
program](https://github.com/lh3/minimap).
<!--more-->

> Minimap is an experimental tool to efficiently find multiple approximate
mapping positions between two sets of long sequences, such as between reads
and reference genomes, between genomes and between long noisy reads. By
default, it is tuned to have high sensitivity to 2kb matches around 20%
divergence but with low specificity. Minimap does not generate alignments as
of now and because of this, it is usually tens of times faster than mainstream
aligners. With four CPU cores, minimap can map 1.6Gbp PacBio reads to human in
2.5 minutes, 1Gbp PacBio E. coli reads to pre-indexed 9.6Gbp bacterial genomes
in 3 minutes, to pre-indexed >100Gbp nt database in ~1 hour (of which ~20
minutes are spent on loading index from the network filesystem; peak RAM:
10GB), map 2800 bacteria to themselves in 1 hour, and map mouse genome to
human in 20 minutes (with one CPU as multi-threading is ineffective for
chromosome-long queries). Minimap can also find long matches between 1Gbp E.
coli reads in one minute, though the sensitivity is probably not good enough.

The algorithm appears to be another elegant application of minimizer. For
previous uses, please check -

[2014 The Year of Minimizers in
Bioinformatics](http://www.homolog.us/blogs/blog/2014/04/06/2014-the-year-of-
minimizers-in-bioinformatics/), [Minimizer Revolution Continues with KMC-2
K-mer Counter](http://www.homolog.us/blogs/blog/2014/07/11/minimizer-
revolution-continues-with-kmc-2-k-mer-counter/).

> Indexing. Collect all (w,k)-minimizers in a batch (-I=4 billion bp) of
target sequences and store them in a hash table. Mark top -f=0.1% of most
frequent minimizers as repeats. Minimap uses invertible hash function to avoid
taking ploy-A as minimizers.

For each query, collect all (w,k)-minimizers and look up the hash table for
matches (qi,ti,si), where qi is the query position, ti the target position and
si indicates whether the minimizer match is on the same strand.

For matches on the same strand, sort by {qi-ti} and then cluster matches
within a -r=500bp window. Minimap merges two windows if 75% of minimizer
matches overlap. For matches on different strands, sort {qi+ti} and apply a
similar clustering procedure. This is inspired by the Hough transformation.

For each cluster, sort (qi,ti) by qi and solve a longest increasing sequence
problem for ti. This finds the longest co-linear matching chain. Break the
chain whenever there is a gap longer than -g=10000.

Output the start and end of the chain if it contains -c=4 or more minimizer
matches.

Go to 1 and rewind to the first record of query if there are more target
sequences; otherwise stop.

