---
title: Today's Highlights - "A Guide for the Lonely Bioinformatician"
tags: []
categories:
- blog
---
A.
<!--more-->

At the other extreme from [BGI's 4000 member
team](http://www.homolog.us/blogs/2013/04/23/bgis-youth-culture/), some
bioinformaticians are suffering alone in various research labs. Mick Watson
sends a helpful hand -

[A guide for the lonely
bioinformatician](http://biomickwatson.wordpress.com/2013/04/23/a-guide-for-
the-lonely-bioinformatician/)

1\. Make friends with local bioinformatics groups

2\. Talk to your computing group

3\. Obtain clear expectations

4\. Rewrite your job description

5\. Papers

6\. Attend bioinformatics meetings

7\. Try first, ask later

How about 'threaten to quit and join Facebook' every once in a while? :)

B.

[Comparing DNA sequence collections by direct comparison of compressed text
indexes](http://arxiv.org/abs/1304.5535) h/t:@lexnederbragt

> Popular sequence alignment tools such as BWA convert a reference genome to
an indexing data structure based on the Burrows-Wheeler Transform (BWT), from
which matches to individual query sequences can be rapidly determined. However
the utility of also indexing the query sequences themselves remains relatively
unexplored. Here we show that an all-against-all comparison of two sequence
collections can be computed from the BWT of each collection with the BWTs held
entirely in external memory, i.e. on disk and not in RAM. As an application of
this technique, we show that BWTs of transcriptomic and genomic reads can be
compared to obtain reference-free predictions of splice junctions that have
high overlap with results from more standard reference-based methods.

Code to construct and compare the BWT of large genomic data sets is available
at this http URL as part of the BEETL library.

C.

[Sequence squeeze: an open contest for sequence
compression](http://www.gigasciencejournal.com/content/2/1/5/abstract) h/t:
@rayanchikhi

>

Next-generation sequencing machines produce large quantities of data which are
becoming increasingly difficult to move between collaborating organisations or
even store within a single organisation. Compressing the data to assist with
this is vital, but existing techniques do not perform as well as might be
expected. The need for a new compression technique was identified by the
Pistoia Alliance who commissioned an open innovation contest to find one. The
dynamic and interactive nature of the contest led to some novel algorithms and
a high level of competition between participants.

D.

[SW# - GPU enabled exact alignments on genome
scale](http://arxiv.org/abs/1304.5966)

> Sequence alignment is one of the oldest and the most famous problems in
bioinformatics. Even after 45 years, for one reason or another, this problem
is still actual; current solutions are trade-offs between execution time,
memory consumption and accuracy. We purpose SW#, a new CUDA GPU enabled and
memory efficient implementation of dynamic programming algorithms for local
alignment. In this implementation indels are treated using the affine gap
model. Although there are other GPU implementations of the Smith-Waterman
algorithm, SW# is the only publicly available implementation that can produce
sequence alignments on genome-wide scale. For long sequences, our
implementation is at least a few hundred times faster than a CPU version of
the same algorithm.

