---
title: Compressed Gk Arrays for K-mer Counting
tags: []
categories:
- blog
---
Edit. Before we proceed with the commentary, Rayan suggested
<!--more-->

Here is a really nice paper that will push the state of the art in genome
assembly (h/t: Rayan Chikhi).

\----------------------

Edit. Before we proceed with the commentary, Rayan suggested that the title is
too narrow.

>

You should change the title: the main purpose of compressed gk arrays is

not kmer counting.

It is a bit misleading that they compare against jellyfish. In fact,

they're comparing against the jellyfish hash table (that is used as a k-mer

index).

The purpose of compressed gk arrays is to make queries on reads, it's an

index.

\---------------------------------

Paper is available here -

[Scalable and Versatile k-mer Indexing for High-Throughput Sequencing
Data](http://hal.archives-ouvertes.fr/docs/00/80/61/03/PDF/cgka-RR-2013.pdf)

> Philippe et al. (2011) proposed a data structure called Gk ar- rays for
indexing and querying large collections of high-throughput sequencing data in
main-memory. The data structure supports versa-tile queries for counting,
locating, and analysing the coverage pro le of k-mers in short-read data. The
main drawback of the Gk arrays is its

space-consumption, which can easily reach tens of gigabytes of main-memory
even for moderate size inputs. We propose a compressed variant of Gk arrays
that supports the same set of queries, but in both near-optimal time and
space. In practice, the compressed Gk arrays scale up to much larger inputs
with highly competitive query times compared to its non-compressed
predecessor. The main applications include variant calling, error correction,
coverage pro ling, and sequence assembly.

An earlier paper from the same group got published in BMC Bioinformatics.

[Querying large read collections in main memory: a versatile data
structure](http://www.biomedcentral.com/content/pdf/1471-2105-12-242.pdf)

How do Gk arrays work?

> Gk arrays index all k-mers occurring within each read of the collection1
using a modi ed sux array and complementary tables [21]. It takes advantage
from the fact that reads are often compared against themselves and that
queried k-mers are taken from a read and can be given by a starting position
rather than in extenso. Gk arrays o ers seven types of locate and counting
queries: either for getting the read identi ers in which a k-mer occurs
(Q1/Q2), occurs at most once (Q5/Q6), and the occurrence positions with (Q7)
or without this restriction (Q3/Q4). Table 1 gives an overview of the queries
and theoretical properties of the data structure. Gk

arrays uses a space proportional to the length of the read collection. Hence,
indexing for instance a metagenomics dataset will exhaust the main memory of
most computers. Gk arrays are also limited to queries on a single k value.

