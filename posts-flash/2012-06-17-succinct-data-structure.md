---
title: Gossamer - 'Succinct' data structure for efficient storage of de Bruijn graphs
tags: []
categories:
- blog
---
In [our comment section](http://www.homolog.us/blogs/2012/06/08/nosql-
databases-for-bioinformatics/), reader Torsten Seemann ([of Velvet Optimizer
fame](http://bioinformatics.net.au/software.velvetoptimiser.shtml)) mentioned
an interesting paper on efficient storage of de Bruijn graphs that is worth
mentioning. The paper is titled ["Succinct data structures for assembling
large
genomes"](http://bioinformatics.oxfordjournals.org/content/27/4/479.full), and
it uses an entropy-compressed data structure to efficiently store de Bruijn
graphs. Those with no patience to read paper can download their [Gossamer
software](http://www.genomics.csse.unimelb.edu.au/product-gossamer.php), and
try it out.
<!--more-->

![](http://www.homolog.us/blogs/wp-content/uploads/2012/06/gossamer-
300x134.png)

The problem it solves is familiar to all bioinformaticians starting to work on
NGS data. In a nutshell,

1\. Mr. Bioinformatician worked on genome sequences for many years, but never
saw data from high-throughput sequencing. Naturally, when he heard 512 Gigs,
he thought of size of hard-drive, not RAM.

2\. He received four large hiSeq files on a mystery genome or transcriptome
from his collaborator Dr. Biologist.

3\. He downloaded and installed a popular program (Velvet, ABySS, SOAPdenovo,
Trinity), found instructions on how to run and tried on 'mystery' libraries.
This was when the fun began. Very soon he found out that the real challenge of
analyzing NGS data was in being able to process them efficiently within
available computational resources. On ordinary (and even some extra-ordinary)
servers, NGS programs ran out of memory space very fast.

Amateur solution is to remove reads arbitrarily and run the programs on
smaller libraries to fit memory. That approach is inefficient, because it
removes useful information by cutting signal and noise equally.

Smart researchers are pursuing five strategies to handle large volume of NGS
data.

A. **Hardware improvement** \- Buy a computer with large RAM (not scalable),
use MPI or Hadoop (scalable).

B. **Smart packing of de Bruijn graph into smaller memory/storage space** \-
Gossamer fits into this category. Other approaches are discussed in Gossamer
paper linked above.

C. **Intelligent removal of reads** \- As an example, [we
discussed](http://www.homolog.us/blogs/2012/04/02/digital-normalization-from-c
-titus-brown/) digital normalization approach by Titus Brown in an earlier
commentary.

D. **Intelligent removal of k-mers** \- In a forthcoming commentary, we will
discuss a new paper on 'SparseAssembler'.

Given that our last few commentaries were on Shannon's research on information
theory, it is worth mentioning that Gossamer reaches theoretically close to
lowest bound on optimal storage by using entropy-compression. We did not get
too much time to elaborate on the concept of entropy used in information
theory in our commentary on ['What is in the
news'](http://www.homolog.us/blogs/2012/06/16/what-is-in-the-news/), but you
can learn more about it from the web-pages linked from there.

