---
title: scTurtle Algorithm for Kmer Counting
tags: []
categories:
- blog
---
In [our previous commentary on k-mer
counting](http://www.homolog.us/blogs/blog/2014/04/07/kmer-
counting-a-2014-recap/), [one program was mentioned peripherally](http://bioin
formatics.rutgers.edu/Static/Publications/kmc_bioinformatics.pdf), because we
knew little about it. On further reading, we find the paper worth mentioning
in a separate commentary, because it brings a number of new concepts to
bioinformatics.
<!--more-->

In simple language, the approach can be described as 'modified BFcounter'.

> First we use a Bloom ?lter to identify the k-mers that were seen at least
twice (with a small false positive rate). To count the frequency of these
k-mers, we use an array of items containing a k-mer and its count. These are
the two main components of our tool. Once the counts are computed, we can
output the k-mers having frequency greater than the chosen cutoff.

The devil is, of course, in the details.

First, they use "Pattern-blocked Bloom Filter". What is that? It is a new
cache-efficient implementation for Bloom filters [developed by a German
group](http://algo2.iti.kit.edu/singler/publications
/cacheefficientbloomfilters-wea2007.pdf). The paper is a must-read.

> A Bloom filter is a very compact data structure that supports approximate
membership queries on a set, allowing false positives. We propose several new
variants of Bloom filters and replacements with similar functionality. All of
them have a better cache-efficiency and need less hash bits than regular Bloom
filters. Some use SIMD functionality, while the others provide an even better
space efficiency. As a consequence, we get a more flexible trade-off between
false positive rate, space efficiency, cache-efficiency, hash-efficiency, and
computational effort. We analyze the efficiency of Bloom filters and the
proposed replacements in detail, in terms of the false positive rate, the
number of expected cache misses, and the number of required hash bits. We also
describe and experimentally evaluate the performance of highly-tuned
implementations. For many settings, our alternatives perform better than the
methods proposed so far.

The second innovation of the paper is a novel sort-and-count method. Is is
similar to run-length encoding.

>

Counting frequencies with sorting and compaction

Counting frequencies with sorting and compaction Our next objective is to
count the frequencies of the frequent k-mers. The basic idea is to store the
frequent k-mers in an array A of size> n, where n is the number of frequent
items. When this array fills up, we sort the items by the k-mer values. This
places the items with the same k-mer next to each other in the array. Now, by
making a linear traversal of the array, we can replace multiple items with the
same k-mer with one item where a count field represents how many items were
merged which is equal to how many times this k-mer was seen; see Figure 1.
Note that, this is very similar to run length encoding.

The paper also claimed that DSK was not as fast as reported.

> Rizk et al. (2013) claimed DSK to be faster than BFCounter, but on our
machine, which had a 18TB Raid-6 storage system of 2TB SATA disks, it proved
to be slower (1591 mins vs. 1012 mins for the GG dataset). Rizk et al. (2013)
reported using more efficient storage systems (like SSD), the lack of which in
our machine might explain DSKs poor performance in our experiments.

Not sure why they had that bad experience, because [Titus Brown's benchmarks
found DSK faster than BFcounter](http://www.homolog.us/blogs/blog/2014/04/07
/kmer-counting-a-2014-recap/). Titus Brown also found sTurtle as good as it
claimed to be. So, it is definitely a top-rated kmer counter.

