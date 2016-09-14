---
title: Efficient Online k-mer Counting using a Probabilistic Data Structure
tags: []
categories:
- blog
---
The topic of k-mer counting is hot again !! Titus Brown's lab posted a new
paper on k-mer counting at arxiv and will submit it to PLOS One.
<!--more-->

[These are not the k-mers you are looking for: efficient online k-mer counting
using a probabilistic data structure](http://arxiv.org/abs/1309.2975)

> K-mer abundance analysis is widely used for many purposes in sequence
analysis, including data preprocessing for de novo assembly, repeat detection,
and sequencing coverage estimation. We present the khmer software package for
fast and memory efficient online counting of k-mers in sequencing data sets.
Unlike previous methods based on data structures such as hash tables, suffix
arrays, and trie structures, khmer relies entirely on a simple probabilistic
data structure, a CountMin Sketch. The CountMin Sketch permits online updating
and retrieval of k-mer counts in memory which is necessary to support
streaming k-mer analysis algorithms. On sparse data sets this data structure
is considerably more memory efficient than any exact data structure. In
exchange, the use of a CountMin Sketch introduces a systematic overcount for
k-mers; moreover, only the counts, and not the k-mers, are stored. Here we
analyze the speed, the memory usage, and the miscount rate of khmer for
generating k-mer frequency distributions and retrieving k-mer counts for
individual k-mers. We also compare the performance of khmer to several other
k-mer counting packages, including Tallymer, Jellyfish, and DSK. Finally, we
examine the effectiveness of profiling sequencing error, k-mer abundance
trimming, and digital normalization of reads in the context of high khmer
error rates. Khmer is implemented in C++ wrapped with a Python interface,
offers a tested and robust API, and is freely available under the BSD license
at github.com/ged-lab/khmer.

The most interesting aspect of the paper is not the topic, but its first
author [Qingpeng Zhang](http://www.cse.msu.edu/~qingpeng/) from China. [From
his CV](https://www.msu.edu/~qingpeng/QingpengZhangMSU_CV.pdf), it appears
that he worked with the older BGI and then Jing-Dong Jackie Han lab before
moving to US. Clearly it is becoming difficult to do mathematically intensive
science in USA without getting researcher from China, and Count-min sketch is
not like solving a Hamiltonian. The other interesting aspect - the CV and
webpage does not have his picture, which we liked to post here.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/09/Capture6-300x154.png)

To learn more about [count-min
sketch](http://en.wikipedia.org/wiki/Count%E2%80%93min_sketch), please start
with wiki -

> The Countmin sketch (or CM sketch) is a probabilistic sub-linear space
streaming algorithm which can be used to summarize a data stream in many
different ways. The algorithm was invented in 2003 by Graham Cormode and S.
Muthu Muthukrishnan.[1]

Countmin sketches are somewhat similar to Bloom filters; the main distinction
is that Bloom filters represent sets, while CM sketches represent multisets
and frequency tables.

We will write more after going through the article more carefully. In the
meanwhile, the readers will find the following links helpful -

[New paper posted -- "These are not the k-mers you are looking
for"](http://ivory.idyll.org/blog/2013-khmer-counting-paper.html)

[These are not the k-mers you are looking for: efficient online k-mer counting
using a probabilistic data structure](http://haldanessieve.org/2013/09/13
/these-are-not-the-k-mers-you-are-looking-for-efficient-online-k-mer-counting-
using-a-probabilistic-data-structure/)

