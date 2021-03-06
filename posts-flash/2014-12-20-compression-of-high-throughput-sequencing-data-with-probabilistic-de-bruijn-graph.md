---
title: Compression of High Throughput Sequencing Data with Probabilistic de Bruijn
  Graph
tags: []
categories:
- blog
---
@RayanChikhi mentioned in twitter about [this new paper](http://arxiv.org/abs/
1412.5932?utm_source=twitterfeed&utm_medium=twitter) \-
<!--more-->

"A super-efficient de novo read compression algorithm (Leon) from
@GuillaumeRizk et al. Paper on #arXiv"

The method is to build de Bruijn graph and then store each read as a path
within the graph. A Bloom-filter based data structure is chosen to store the
graph. Full abstract is shown below.

> Motivation: Data volumes generated by next-generation sequencing technolo-
gies is now a major concern, both for storage and transmission. This triggered
the need for more efficient methods than general purpose compression tools,
such as the widely used gzip. Most reference-free tools developed for NGS data
compression still use general text compression methods and fail to benefit
from algorithms already designed specifically for the analysis of NGS data.
The goal of our new method Leon is to achieve compression of DNA sequences of
high throughput sequencing data, without the need of a reference genome, with
techniques derived from existing assembly principles, that possibly better
exploit NGS data redundancy. Results: We propose a novel method, implemented
in the software Leon, for compression of DNA sequences issued from high
throughput sequencing technologies. This is a lossless method that does not
need a reference genome. Instead, a reference is built de novo from the set of
reads as a probabilistic de Bruijn Graph, stored in a Bloom filter. Each read
is encoded as a path in this graph, storing only an anchoring kmer and a list
of bifurcations indicating which path to follow in the graph. This new method
will allow to have compressed read files that also already contain its
underlying de Bruijn Graph, thus directly re-usable by many tools relying on
this structure. Leon achieved encoding of a C. elegans reads set with 0.7
bits/base, outperforming state of the art reference-free methods.
Availability: Open source, under GNU affero GPL License, available for
download at this http URL

Rob patro pointed out similarities with the following paper -

[Compression of short-read sequences using path
encoding](http://biorxiv.org/content/early/2014/06/24/006551)

> Storing, transmitting, and archiving the amount of data produced by next
generation sequencing is becoming a significant computational burden. For
example, large-scale RNA-seq meta-analyses may now routinely process tens of
terabytes of sequence. We present here an approach to biological sequence
compression that reduces the difficulty associated with managing the data
produced by large-scale transcriptome sequencing. Our approach offers a new
direction by sitting between pure reference-based compression and reference-
free compression and combines much of the benefit of reference-based
approaches with the flexibility of de novo encoding. Our method, called path
encoding, draws a connection between storing paths in de Bruijn graphs --- a
common task in genome assembly --- and context-dependent arithmetic coding.
Supporting this method is a system, called a bit tree, to compactly store sets
of kmers that is of independent interest. Using these techniques, we are able
to encode RNA-seq reads using 3% -- 11% of the space of the sequence in raw
FASTA files, which is on average more than 34% smaller than recent competing
approaches. We also show that even if the reference is very poorly matched to
the reads that are being encoded, good compression can still be achieved.

The main difference between two papers is in the form of data structure (Bloom
filter vs bit vector). Also, the later paper uses some kind of reference,
although it can be of very poor quality, whereas the former paper simply uses
the dBG.

Also note that the authors of KMC developed a minimizer-based compression
method -

[Minimizer Success Disk-based Genome Sequencing Data
Compression](http://www.homolog.us/blogs/blog/2014/05/28/minimizer-success-
disk-based-genome-sequencing-data-compression/)

> Our method makes use of a conceptually simple and easily parallelizable idea
of minimizers, to obtain 0.376 bits per base as the compression ratio.

