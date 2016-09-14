---
title: POA and Nanopolish
tags: []
categories:
- blog
---
This is an old (well-cited) paper from 2002, but the algorithm is finding
plenty of use lately with SPAdes and Jared Simpson's nanopolish. I have not
checked what algorithm Jason Chin uses in his
[pbdagcon](https://github.com/PacificBiosciences/pbdagcon).
<!--more-->

[Multiple sequence alignment using partial order
graphs](http://bioinformatics.oxfordjournals.org/content/18/3/452.short)

> Motivation: Progressive Multiple Sequence Alignment (MSA) methods depend on
reducing an MSA to a linear profile for each alignment step. However, this
leads to loss of information needed for accurate alignment, and gap scoring
artifacts.

Results: We present a graph representation of an MSA that can itself be
aligned directly by pairwise dynamic programming, eliminating the need to
reduce the MSA to a profile. This enables our algorithm (Partial Order
Alignment (POA)) to guarantee that the optimal alignment of each new sequence
versus each sequence in the MSA will be considered. Moreover, this algorithm
introduces a new edit operator, homologous recombination, important for
multidomain sequences. The algorithm has improved speed (linear time
complexity) over existing MSA algorithms, enabling construction of massive and
complex alignments (e.g. an alignment of 5000 sequences in 4 h on a Pentium
II). We demonstrate the utility of this algorithm on a family of multidomain
SH2 proteins, and on EST assemblies containing alternative splicing and
polymorphism.

Availability: The partial order alignment program POA is available at
http://www.bioinformatics.ucla.edu/poa.

\---------------------------

Jared posted his code and instructions
[here](https://github.com/jts/nanopolish).

>

**Brief usage instructions**

The pipeline is still a prototype so it is fragile at the moment. It will be
revised for general use after we submit the paper.

The reads that are input into the HMM must be output as a .fa file by
poretools. This is important as poretools writes the path to the original
.fast5 file (containing the signal data) in the fasta header. These paths must
be correct or nanopolish cannot find the events for each read. Let's say you
have exported your reads to reads.fa and you want to polish draft.fa. You
should run:

make -f consensus.make READS=reads.fa ASSEMBLY=draft.fa

This will map the reads to the assembly with bwa mem -x ont2d and export a
file mapping read names to fast5 files.

