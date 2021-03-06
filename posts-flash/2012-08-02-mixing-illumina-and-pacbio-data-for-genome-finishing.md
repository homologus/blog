---
title: Mixing Illumina and PacBio Data for Genome Finishing
tags:
- Pacbio
categories:
- blog
---
PacBio machines give long reads, but the sequences are very noisy (error rate
1 in 10). It may be possible to improve the quality of PacBio sequences by
multiple rounds of resequencing, but a new (and cheaper) cleanup alternative
is emerging that uses short high-quality Illumina reads. [We earlier
discussed](http://www.homolog.us/blogs/2012/05/03/the-genome-assembly-process-
and-how-pac-bio-can-help/) how the method works based on slides from Michael
Schatz, but now the readers can find more information from two recently
published papers.
<!--more-->

1\. [Finished bacterial genomes from shotgun sequence data](http://genome.cshl
p.org/content/early/2012/07/24/gr.141515.112.full.pdf+html)

A paper published in Genome Research from Broad Institute ALLPATHS team
discussed how they automated the expensive finishing step of bacterial genomes
by combining data from two technologies.

> By applying a new laboratory design and new assembly algorithm to sixteen
samples, we demonstrate that assemblies exceeding finished quality can be
obtained from whole-genome shotgun data and automated computation. Cost and
time requirements are thus dramatically reduced.

2\. [Hybrid error correction and de novo assembly of single-molecule
sequencing reads](http://www.nature.com/nbt/journal/v30/n7/full/nbt.2280.html)

This paper is from Michael Schatz's group.

> We introduce a correction algorithm and assembly strategy that uses short,
high-fidelity sequences to correct the error in single-molecule sequences. We
demonstrate the utility of this approach on reads generated by a PacBio RS
instrument from phage, prokaryotic and eukaryotic whole genomes, including the
previously unsequenced genome of the parrot Melopsittacus undulatus, as well
as for RNA-Seq reads of the corn (Zea mays) transcriptome. Our long-read
correction achieves >99.9% base-call accuracy, leading to substantially better
assemblies than current sequencing strategies: in the best example, the median
contig size was quintupled relative to high-coverage, second-generation
assemblies.

Readers may also look at [PacBioToCA
software](http://sourceforge.net/apps/mediawiki/wgs-
assembler/index.php?title=PacBioToCA) from the same group.

Needless to say, neither paper answers, or can possibly answer, an important
question regarding PacBio in many people's mind. Can any algorithm turn the
[slope of this curve](http://stockcharts.com/h-sc/ui?s=PACB&p=D&yr=3&mn=0&dy=0
&id=p59416164893) upward?

