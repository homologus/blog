---
title: Quip, Minia, SlimGene and Titus Brown's paper on Scaling Metagenome
tags:
- metagenome
- Minia
- Bloom filter
categories:
- blog
---
With terabytes of NGS data pouring in from all sources, storage of reads has
become an important issue. The second issue is to fit in a de Bruijn graph
consisting of large number of k-mers into limited RAM space so that genome or
transcriptome assembly can be performed. In this commentary, we will discuss
few cutting edge algorithms to solve the above problems.
<!--more-->

An intelligent reader may see commonality between the two problems. To a
computer processor, RAM and hard drive are merely two different storage
devices with one having larger access time than other. So, it is possible for
researchers solving those two apparently distinct problems to share few common
tools. Of course, RAM and hard drive behave differently (with one losing all
data and other not) if the computer crashes or gets rebooted, but how many
bioinformatics researchers use Windows machine anyway :)?

1\. **[SlimGene**](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3123913/?tool=p
ubmed)

Typically, large fasta or fastq files can be compressed using standard
programs such as gzip or bzip2. SlimGene does even better by mapping the reads
on to reference human genome and using mapped positions in compressed file
instead of the entire reads.

The part we found most interesting about SlimGene was its discussion on
compression of quality scores. Quality scores take large space in fastq files
and they cannot be discarded given that many variant calling programs use them
to decide whether a mismatched nucleotide is really a SNP or a sequencing
error. However, is it necessary to have quality scores recoverable as original
after a compression-decompression cycle?

The above question does not arise for compressing fasta files, because there
will be riots started among bioinformaticians, if scientist A compresses human
genome using an algorithm, sends it to scientist B over the network, and
scientist B finds few As changed to Gs after decompression. However, quality
scores are not so sacrosanct, and SlimGene showed that it can get significant
improvement in compression without much loss in analysis, if quality scores
are compressed using a lossy algorithm.

2\. **[Quip**](https://github.com/dcjones/quip#readme)

Quip, a sequence compression tool developed by researchers from University of
Washington, can reduce large fastq or SAM/BAM files to 15% of original size.
It follows similar reference-based compression strategy as SlimGene, but with
an important improvement.

> In addition, we implement reference-based compression in which aligned reads
are stored a positions within a genome. And, when no reference genome is
available, an extremely efficient de novo assembly algorithm can transparently
construct one.

How does Quip assemble the reference genome given that the problem of assembly
itself is requires a lot of RAM and computing time? It forms a probabilistic
de Bruijn graph using Bloom filter and then uses a greedy approach to build
contigs.

> Given a probabilistic de Bruijn graph, we assemble contigs using a very
simple greedy approach. A read sequence is used as a seed and extended on both
ends one nucleotide at a time by repeatedly finding the most abundant k-mer
that overlaps the end of the contig by k-1 bases. More sophisticated
heuristics have been developed, but we choose to focus on efficiency,
sacrificing a degree of accuracy.

[Titus](http://ivory.idyll.org/blog/science-f-yeah.html)

Titus Brown's paper on "Scaling metagenome assembly with probabilistic de
Bruijn graphs" developed an approach similar to Quip for handling large de
Bruijn graph in less RAM using Bloom filter-based probabilistic approach. From
their abstract -

> Here we introduce a memory-efficient graph representation with which we can
analyze the k-mer connectivity of metagenomic samples. The graph
representation is based on a probabilistic data structure, a Bloom filter,
that allows us to efficiently store assembly graphs in as little as 4 bits per
k-mer, albeit inexactly. We show that this data structure accurately
represents DNA assembly graphs in low memory.

[Minia](http://minia.genouest.org/)

Minia also uses Bloom filters to store de Bruijn graphs in limited space, but
it has an additional structure to remove critical false positives, and claimed
to performe a complete de novo assembly of human genome from short reads using
5.7 Gb of memory in 23 hours.

Here is more on the special structure to remove critical false positives from
their [paper](http://minia.genouest.org/minia.pdf) \-

> **The cFP structure**

Our contribution is a mechanism that avoids false branching. Specifically, we
propose to detect and store false positive elements which are responsible for
false branching, in a separate structure. To this end, we introduce the cFP
structure of critical False Positives k-mers, implemented with a standard set
allowing fast membership test. Each query to the Bloom filter is modified such
that the yes answer is returned if and only if the Bloom filter answers yes
and the element is not in cFP.

Naturally, if cFP contained all the false positives elements, the benefits of
using a Bloom filter for memory efficiency would be lost. The key observation
is that the k-mers which will be queried when traversing the graph are not all
possible k-mers.

