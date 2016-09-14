---
title: Chinese Hamster Genome Sequenced from Sorted Chromosomes
tags: []
categories:
- blog
---
[Link](http://www.nature.com/nbt/journal/v31/n8/full/nbt.2645.html)
<!--more-->

What is more elegant, using chromosome sorting to improve quality of de novo
assembly or using correspondence format related to previously published genome
paper to publish in Nature Biotech? On both counts, we are impressed with the
authors.

> Current NGS technology yields short-read sequences typically in the range of
100500 bp, so that common repeats cannot be assembled and the precise location
of duplicated sequences is likely to be missed5. De novo assembly generates,
on average, scaffolds of 12 Mb if genome coverage is sufficiently high (50- to
100-fold). As chromosomes are several fold larger (typically 90-200 Mb),
chromosomal rearrangements and translocations can be captured only in part.

Here, we address this dilemma by isolating individual chromosomes by flow
cytometric cell sorting, followed by NGS of the obtained material in separate
sequencing reactions. After curation and assembly, the resulting scaffolds can
be assigned to specific chromosomes. We applied our approach to cells from the
Chinese hamster strain 17A/GY and came across several challenges, such as
cross-contamination by chromosomes that were too close in the flow histogram
and which required a bioinformatic procedure for curation (Fig. 1). The most
severely affected chromosomes in this respect were chromosomes 5 and 6.
Chromosomes 9 and 10 could only be separated as a pool and chromosome Y was
not sorted at all. For library construction, we obtained 80620 ng of DNA for
each sorted chromosome and prepared, in addition, a 5,000-bp mate-pair
sequencing library from whole genome DNA. We sequenced the libraries on an
Illumina (San Diego) Genome Analyzer IIx, using TrueSeq PE Cluster Kit v5-CS-
GA and TrueSeq SBS Kit v5-GA and generated ~70-fold genome coverage, assuming
a genome size of 2.8 Gb for the Chinese hamster6. Subsequently, 1.4 billion
reads were assembled into a draft sequence for the separated chromosomes using
ALLPATHS-LG7. As mentioned above, sequencing libraries from separated
chromosomes might be contaminated with sequences from other hamster
chromosomes. The separated chromosome assemblies were therefore analyzed to
identify and eliminate contaminating scaffolds from the data. This filtering
led to high-quality assemblies of separated Chinese hamster chromosomes with
the total number of scaffolds ranging from 517 for chromosome 8 to 5,348 for
chromosomes 9+10, and a total genome size of 2.33 Gb (Table 1).

