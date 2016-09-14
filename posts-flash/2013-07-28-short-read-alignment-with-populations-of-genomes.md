---
title: Short Read Alignment with Populations of Genomes
tags: []
categories:
- blog
---
How to map short reads to 1000s of genomes? The naive solution faces [serious
problems](http://bioinformatics.oxfordjournals.org/content/29/13/i361.long).
<!--more-->

> The naive solution to this problem is to use the existing fast aligners to
map new read samples to all available genomes individually. The state-of-the-
art aligners, albeit much faster than their predecessors, still take 35 h to
map 12.2 million reads to a human genome on a single core processor (Li and
Durbin, 2009), so spending Graphic more time (roughly a year) to map those
reads to all the genomes currently in the 1000 Genomes Project is not a
realistic solution, especially as this time will scale linearly with the
number of genomes in the collection. Furthermore, even though the space
required to store the BWT-related data structures of each genome can be
significantly reduced using various compression techniques (Hon et al., 2007),
the total amount of space required for storing all the available genome data
is considerable. Finally, this solution does not take into account the
scenario where the newly sequenced genome has a novel haplotype of several
nearby SNPs (i.e. when the newly sequenced genome contains a combination of
SNPs that do not occur together in any known genome individually).

Solutions? (Thanks to Mark Chaisson for pointing out) -

**2009 version -**

[Simultaneous alignment of short reads against multiple
genomes](http://genomebiology.com/2009/10/9/R98)

> Genome resequencing with short reads generally relies on alignments against
a single reference. GenomeMapper supports simultaneous mapping of short reads
against multiple genomes by integrating related genomes (e.g., individuals of
the same species) into a single graph structure. It constitutes the first
approach for handling multiple references and introduces representations for
alignments against complex structures. Demonstrated benefits include access to
polymorphisms that cannot be identified by alignments against the reference
alone. Download GenomeMapper at http://1001genomes.org.

**2011 edition (locked paper, not mentioning it)**

**2013 edition -**

[Short read alignment with populations of
genomes](http://bioinformatics.oxfordjournals.org/content/29/13/i361.long)

> Summary: The increasing availability of high-throughput sequencing
technologies has led to thousands of human genomes having been sequenced in
the past years. Efforts such as the 1000 Genomes Project further add to the
availability of human genome variation data. However, to date, there is no
method that can map reads of a newly sequenced human genome to a large
collection of genomes. Instead, methods rely on aligning reads to a single
reference genome. This leads to inherent biases and lower accuracy. To tackle
this problem, a new alignment tool BWBBLE is introduced in this article. We
(i) introduce a new compressed representation of a collection of genomes,
which explicitly tackles the genomic variation observed at every position, and
(ii) design a new alignment algorithm based on the BurrowsWheeler transform
that maps short reads from a newly sequenced genome to an arbitrary collection
of two or more (up to millions of) genomes with high accuracy and no inherent
bias to one specific genome.

Availability: http://viq854.github.com/bwbble.

The difference between the first (2009) and the last (2013) paper is that the
last one used Burrows-Wheeler transform. The innovation was in being able to
compress variant information in 1000 genomes into one genome and run BWT on
that. For example, they converted all SNP locations from A/T/G/C to IUPAC
code. That was easy. For indels, they took the longest version and merged the
shorter ones on top of it. Overall, they summarized everything into one super-
genome, indexed it using traditional BWT indexing method and ran alignment of
reads.

The similarity between two papers is that they both consider BWA to be state-
of-the-art despite being written with a time gap of four years. We are not
sure whether that reflects on the stagnant nature of bioinformatics field, the
extra-ordinary abilities of Heng Li, or something else.

> We compared the performance of BWBBLE with the state-of-the-art BWT-based
single-genome aligner, BWA (Li and Durbin, 2009).

