---
title: dipSpades Beats Haplomerger Hands Down in Diploid Assembly
tags: []
categories:
- blog
---
Yana Safonova, Anton Bankevich and Pavel Pevzner wrote a new paper that is
[accepted for RECOMB](http://www.compbio.cmu.edu/recomb/acceptedpapers.html)
\- "DipSPAdes: Assembler for Highly Polymorphic Diploid Genomes".
<!--more-->

From [dipSpades
website](http://spades.bioinf.spbau.ru/release3.0.0/dipspades_manual.html),

> dipSPAdes is a genome assembler designed specifically for diploid highly
polymorphic genomes based on SPAdes. It takes advantage of divergence between
haplomes in repetitive genome regions to resolve them and construct longer
contigs. dipSPAdes produces consensus contigs (representing a consensus of
both haplomes for the orthologous regions) and performs haplotype assembly.
Note that dipSPAdes can only benefit from high polymorphism rate (at least
0.4%). For the data with low polymorphism rate no improvement in terms of N50
vs consentional assemblers is expected.

The assembly pipeline consists of three steps -

1\. Assembly of haplocontigs (contigs representing both haplomes).

2\. Consensus contigs construction.

3\. Haplotype assembly.

Here is an example of how the complex regions are resolved.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/03/Capture1-300x216.png)

The benchmarks look very impressive, as you can find in the following table.

![Capture](http://www.homolog.us/blogs/wp-content/uploads/2014/03/Capture-
300x85.png)

We expect the real competition to be between technology (all PacBio assembled
by Jason Chin's diploid assembler) and algorithm (short reads + dipSPAdes).

