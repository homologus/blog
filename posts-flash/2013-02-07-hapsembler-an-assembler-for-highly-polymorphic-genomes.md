---
title: Hapsembler - An Assembler for Highly Polymorphic Genomes
tags: []
categories:
- blog
---
[A question came up in Biostars](http://www.biostars.org/p/63047/) \-
<!--more-->

> I'm trying to assemble small (20Mb), diploid fungal genome from MiSeq reads
(~400bp after merging, 100x coverage). The tricky thing: it's heterozygous.
The divergence is ~4%, but there are hundreds (thousands?) loss of
heterozygosity (LOH) regions, accounting in total to almost half of the
genome...Do you know of any assembler (methodology) capable of handling with
such data?

\- and Rayan suggested
[Hapsembler](http://www.cs.toronto.edu/~nild/donmez11.pdf), (Code available
from: [Link](http://compbio.cs.toronto.edu/hapsembler)).

Since we never wrote on Hapsembler, now is a good opportunity to go over the
algorithm and its applicability.

\------------------

Most traditional genome assemblers assume that both chromosomes are identical.
More the genome under consideration moves away from that assumption, more
difficult it is to assemble it from NGS (or even Sanger) sequences using
traditional tools. BGI tried to assemble insanely polymorphic Oyster genome
using SOAPdenovo2 and was not successful. [Then they chemically
broke](http://www.homolog.us/blogs/2012/09/19/pacific-oyster-genome-
published/) the chromosomes into small bacteria-sized pieces and assembled
each piece separately. Those smaller pieces were joined computationally using
SOAPdenovo2c scaffolding algorithm.

Someone writing an assembly program for polymorphic genomes starts with asking
- do we want to retrieve two separate chromosomes, or one single genome that
is mosaic of two difference sequences? It is easy to choose more general
solution, but then the question of sorting out phases is important. That is
not an easy problem to solve along with a new assembly.

Moral of the story - it is very difficult to assemble a highly polymorphic
genomes using traditional assembly programs, unless you know the code inside
out and write loops around various built in assumptions.

\--------------------

Hapsembler works through three stages -

**Alignment module: **

> The alignment module is used to compute pairwise sequence alignments between
reads that obey certain criteria. This procedure employs an efficient kmer
hashing technique to detect overlaps longer than a user defined length.

**Error correction module:**

This initial set of overlaps is used to correct sequencing errors by a
probabilistic error correction procedure based on Naive Bayes. The corrected
reads are then passed through another overlapping stage to compute the final
set of overlaps.

**Graph module:**

> The graph module builds an overlap graph (a.k.a string graph) using the

overlaps reported by the alignment module. This graph is used to construct

path sets representing possible tilings between paired reads. A mate pair
graph

is then constructed in which nodes represent mate pairs, and edges represent

possible overlaps between mate pairs as constrained by the path sets. Finally,

contigs are determined by finding maximal paths in the mate pair graph.

You can find more details [in their
paper](http://www.cs.toronto.edu/~nild/donmez11.pdf).

In this context, readers may also check [HaploMerger: A Software Tool for
Assembling Highly Polymorphic
Genomes](http://www.homolog.us/blogs/2012/07/11/haplomerger-a-software-tool-
for-assembling-highly-polymorphic-genomes/)

\-------------------

On a somewhat related topic, readers may like to learn about [Cortex assembler
from Zamin Iqbal](http://www.homolog.us/blogs/2013/01/11/high-throughput-
microbial-population-genomics-using-the-cortex-variation-assembler/) and read
our earlier commentary titled [Exploring Single-sample SNP and indel Calling
with Whole-Genome Assembly](http://www.homolog.us/blogs/2012/12/12/exploring-
single-sample-snp-and-indel-calling-with-whole-genome-assembly/). If you
really looking for an esoteric graph-based algorithm for sorting out phases,
please try [HapCompass](http://www.homolog.us/blogs/2012/08/28/hapcompass-an-
elegant-use-of-graphs-for-haplotype-assemblyphasing/) from Sorin Istrail's
lab.

