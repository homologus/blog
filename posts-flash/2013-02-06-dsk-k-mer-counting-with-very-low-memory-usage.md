---
title: 'DSK: K-mer Counting with Very Low Memory Usage'
tags: []
categories:
- blog
---
[Minia genome assembly algorithm](http://www.homolog.us/blogs/2012/10/01
/minia-assembly-algorithm-and-french-revolution/), which accomplished the
[unusual feat of assembling human genome in a desktop
computer](http://minia.genouest.org/), used a novel k-mer counting method to
keep memory usage below 4G limit. It was done, because k-mer counting takes
much more RAM than the actual assembly from a reduced set of k-mers.
<!--more-->

Their k-mer counting method is now published as a [separate paper in
Bioinformatics](http://minia.genouest.org/files/dsk_preprint.pdf). We wonder,
whether the name DSK was chosen to show respect to the [French
leader](http://en.wikipedia.org/wiki/Dominique_Strauss-Kahn).

Most important table from the paper is shown below. DSK with SSD appears to
perform as well as Jellyfish, but using only 1/18th as much RAM and 4 threads
instead of 8 in Jellyfish. However, DSK allows you to do k-mer counting for
arbitrary length, whereas Jellyfish is restricted to 32 mers.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/02/Capture2.png)

Here is the abstract:

> Counting all the k-mers (substrings of length k) in DNA/RNA sequencing reads
is the preliminary step of many bioinformatics applications. However, state of
the art k-mer counting methods require that a large data structure resides in
memory. Such structure typically grows with the number of distinct k-mers to
count. We present a new streaming algorithm for k-mer counting, called DSK
(disk streaming of k-mers), which only requires a fixed user-defined amount of
memory and disk space. This approach realizes a memory, time and disk trade-
off. The multi-set of all k-mers present in the reads is partitioned, and
partitions are saved to disk. Then, each partition is separately loaded in
memory in a temporary hash table. The k-mer counts are returned by traversing
each hash table. Low-abundance k-mers are optionally filtered. DSK is the
first approach that is able to count all the 27-mers of a human genome dataset
using only 4.0 GB of memory and moderate disk space (160 GB), in 17.9 h. DSK
can replace a popular k-mer counting software (Jellyfish) on small-memory
servers. AVAILABILITY: http://minia.genouest.org/dsk CONTACT: rayan.chikhi
@ens-cachan.org.

