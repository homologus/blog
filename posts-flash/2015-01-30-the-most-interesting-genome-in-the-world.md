---
title: The Most Interesting Genome in the World
tags: []
categories:
- blog
---
Dear Pacbio,
<!--more-->

We like to propose to sequence the genome of your bioinformatician Jason Chin
for your ['The Most Interesting Genome in the World'
contest](http://www.pacb.com/smrtgrant/). Only picture of him available online
is shown below.

![download](http://www.homolog.us/blogs/wp-
content/uploads/2015/01/download.jpg)

Jason Chin has been writing amazing open access assembly programs including
[HGAP](https://github.com/PacificBiosciences/Bioinformatics-
Training/wiki/HGAP),
[PBdagcon](https://github.com/PacificBiosciences/pbdagcon) and more recently
[Falcon](https://github.com/PacificBiosciences/FALCON). We heard that even
your long-read competitor, who pronounced Pacbio dead, uses his programs in
their analysis.

Sequencing his genome will help us discover the bioinformatics gene, which we
will transfect inside the brain cells of every young biology student to make
sure they can assemble long, noisy reads. Or we can even do CRISPR/cas, which
seems to be the hottest thing around these days. Going forward, we can even
expand this into a larger GWAS project involving those who understand the
importance of long reads and those who do not.

As you can see, the possibilities are endless with this small initial
investment. Therefore, we earnestly request you to give serious consideration
to our proposal.

Sincerely,

Homolog.us Team

\----------------------------------------------------------

> **What is pbdagcon?**

pbdagcon is a tool that implements DAGCon (Directed Acyclic Graph Consensus)
which is a sequence consensus algorithm based on using directed acyclic graphs
to encode multiple sequence alignment.

It uses the alignment information from blasr to align sequence reads to a
"backbone" sequence. Based on the underlying alignment directed acyclic graph
(DAG), it will be able to use the new information from the reads to find the
discrepancies between the reads and the "backbone" sequences. A dynamic
programming process is then applied to the DAG to find the optimum sequence of
bases as the consensus. The new consensus can be used as a new backbone
sequence to iteratively improve the consensus quality.

While the code is developed for processing PacBio(TM) raw sequence data, the
algorithm can be used for general consensus purpose. Currently, it only takes
FASTA input. For shorter read sequences, one might need to adjust the blasr
alignment parameters to get the alignment string properly.

The code and the underlying graphical data structure have been used for some
algorithm development prototyping including phasing reads, pre-assembly and a
work around to generate consensus from intermediate Celera Assembler outputs.

The initial graphical algorithm was a pure python implementation. Cython was
then use to speed it up.

Check out the example/ directory to see how to use it.

> **Falcon**

Falcon: a set of tools for fast aligning long reads for consensus and assembly

The Falcon tool kit is a set of simple code collection which I use for
studying efficient assembly algorithm for haploid and diploid genomes. It has
some back-end code implemented in C for speed and some simple front-end
written in Python for convenience.

