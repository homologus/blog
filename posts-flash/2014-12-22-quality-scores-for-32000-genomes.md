---
title: Quality scores for 32,000 microbial genomes, no eukaryotes
tags: []
categories:
- blog
---
[Link](http://www.standardsingenomics.com/content/9/1/20) (h/t: @hengli)
<!--more-->

> Background

More than 80% of the microbial genomes in GenBank are of draft quality (12,553
draft vs. 2,679 finished, as of October, 2013). We have examined all the
microbial DNA sequences available for complete, draft, and Sequence Read
Archive genomes in GenBank as well as three other major public databases, and
assigned quality scores for more than 30,000 prokaryotic genome sequences.

Results

Scores were assigned using four categories: the completeness of the assembly,
the presence of full-length rRNA genes, tRNA composition and the presence of a
set of 102 conserved genes in prokaryotes. Most (~88%) of the genomes had
quality scores of 0.8 or better and can be safely used for standard
comparative genomics analysis. We compared genomes across factors that may
influence the score. We found that although sequencing depth coverage of over
100x did not ensure a better score, sequencing read length was a better
indicator of sequencing quality. With few exceptions, most of the 30,000
genomes have nearly all the 102 essential genes.

Conclusions

The score can be used to set thresholds for screening data when analyzing all
published genomes and reference data is either not available or not
applicable. The scores highlighted organisms for which commonly used tools do
not perform well. This information can be used to improve tools and to serve a
broad group of users as more diverse organisms are sequenced. Unexpectedly,
the comparison of predicted tRNAs across 15,000 high quality genomes showed
that anticodons beginning with an A (codons ending with a U) are almost non-
existent, with the exception of one arginine codon (CGU); this has been noted
previously in the literature for a few genomes, but not with the depth found
here.

\---------------------------------------

Edit.

For eukaryotes, the assemblers are characterized instead of the genomes. For
example -

[Assessment of de novo assemblers for draft genomes: a case study with fungal 
genomes](http://link.springer.com/article/10.1186/1471-2164-15-S9-S10?utm_cont
ent=buffer736cf&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer)

>

Background

Recently, large bio-projects dealing with the release of different genomes
have transpired. Most of these projects use next-generation sequencing
platforms. As a consequence, many de novo assembly tools have evolved to
assemble the reads generated by these platforms. Each tool has its own
inherent advantages and disadvantages, which make the selection of an
appropriate tool a challenging task.

Results

We have evaluated the performance of frequently used de novo assemblers namely
ABySS, IDBA-UD, Minia, SOAP, SPAdes, Sparse, and Velvet. These assemblers are
assessed based on their output quality during the assembly process conducted
over fungal data. We compared the performance of these assemblers by
considering both computational as well as quality metrics. By analyzing these
performance metrics, the assemblers are ranked and a procedure for choosing
the candidate assembler is illustrated.

Conclusions

In this study, we propose an assessment method for the selection of de novo
assemblers by considering their computational as well as quality metrics at
the draft genome level. We divide the quality metrics into three groups: g1
measures the goodness of the assemblies, g2 measures the problems of the
assemblies, and g3 measures the conservation elements in the assemblies. Our
results demonstrate that the assemblers ABySS and IDBA-UD exhibit a good
performance for the studied data from fungal genomes in terms of running time,
memory, and quality. The results suggest that whole genome shotgun sequencing
projects should make use of different assemblers by considering their merits.
