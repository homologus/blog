---
title: Minimizer Revolution Continues with KMC-2 K-mer Counter
tags: []
categories:
- blog
---
[This paper](http://arxiv.org/abs/1407.1507) had been quite expected from
either the KMC or DSK group, based on the success of minimizers so far (check
- "[2014 The Year of Minimizers in
Bioinformatics](http://www.homolog.us/blogs/blog/2014/04/06/2014-the-year-of-
minimizers-in-bioinformatics/)"). The issue is how to choose the minimizer,
because alphabetical ordering creates a number of problems. Firstly, the sizes
of partitions are unbalanced and low-entropy sequences like AAAAAA get too
many hits. Rayan Chikhi et al. showed that choosing minimizers based on
relative frequency of presence worked better, but that would require knowing
all k-mers, whereas in k-mer counting one attempts to find the k-mers in the
first place. Wood and Salzberg came up with another clever approach based on
randomizing the bits using XOR.
<!--more-->

This paper proposes two novel ideas -

> There are two main ideas behind these improvements. The first is the use of
signatures of k-mers that are a generalization of the idea of minimizers
(Roberts et al., 2004a,b). Signatures allow significant reduction of temporary
disk space. The minimizers were used for the first time for the k-mer counting
in MSPKmerCounter, but our modification significantly reduces the main memory
requirements (up to 35 times) as well as disk space (about 5 times) as
compared to MSPKmerCounter. The second main novelty is the use of (k, x)-mers
(x > 0) for reduction of the amount of data to sort. Simply speaking, instead
of sorting some amount of k-mers we sort a much smaller portion of (k +
x)-mers and then obtain the statistics for k-mers in the postprocessing phase.

We are still in the middle of going through the paper, but presume the second
idea possibly came from their earlier paper on compression mentioned in our
earlier blog post - [Minimizer Success Disk-based Genome Sequencing Data
Compression](http://www.homolog.us/blogs/blog/2014/05/28/minimizer-success-
disk-based-genome-sequencing-data-compression/). In the meanwhile, please feel
free to comment on -

[KMC 2: Fast and resource-frugal k-mer
counting](http://arxiv.org/abs/1407.1507)

> Motivation: Building the histogram of occurrences of every k-symbol long
substring of nucleotide data is a standard step in many bioinformatics
applications, known under the name of k-mer counting. Its applications include
developing de Bruijn graph genome assemblers, fast multiple sequence alignment
and repeat detection. The tremendous amounts of NGS data require fast
algorithms for k-mer counting, preferably using moderate amounts of memory.

Results: We present a novel method for k-mer counting, on large datasets at
least twice faster than the strongest competitors (Jellyfish~2, KMC~1), using
about 12\,GB (or less) of RAM memory. Our disk-based method bears some
resemblance to MSPKmerCounter, yet replacing the original minimizers with
signatures (a carefully selected subset of all minimizers) and using
(k,x)-mers allows to significantly reduce the I/O, and a highly parallel
overall architecture allows to achieve unprecedented processing speeds. For
example, KMC~2 allows to count the 28-mers of a human reads collection with
44-fold coverage (106\,GB of compressed size) in about 20 minutes, on a 6-core
Intel i7 PC with an SSD.

And the world cup goes to Gliwice and Lodz, Poland !

> The presented KMC 2 algorithm is currently the fastest k-mer counter, with
modest resource (memory and disk) requirements. Although the used approach is
similar to the one from MSPKmerCounter, we obtain an order of magnitude faster
processing, due to the following KMC features: replacing the original
minimizers with signatures (a carefully selected subset of all minimizers),
using (k, x)-mers and a highly parallel overall architecture. As opposed to
most competitors, KMC 2 worked stably across a large range of datasets and
test settings.

