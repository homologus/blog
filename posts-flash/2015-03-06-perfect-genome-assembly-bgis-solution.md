---
title: Perfect Genome Assembly - BGI's Solution
tags: []
categories:
- blog
---
We came across [a
paper](http://journal.frontiersin.org/article/10.3389/fgene.2014.00466/full)
co-authored by members of Complete Genomics (bought by BGI) and BGI.
<!--more-->

> Next generation sequencing (NGS) technologies, primarily based on massively
parallel sequencing, have touched and radically changed almost all aspects of
research worldwide. These technologies have allowed for the rapid analysis, to
date, of the genomes of more than 2,000 different species. In humans, NGS has
arguably had the largest impact. Over 100,000 genomes of individual humans
(based on various estimates) have been sequenced allowing for deep insights
into what makes individuals and families unique and what causes disease in
each of us. Despite all of this progress, the current state of the art in
sequence technology is far from generating a perfect genome sequence and much
remains to be understood in the biology of human and other organisms genomes.
In the article that follows, we outline why the perfect genome in humans is
important, what is lacking from current human whole genome sequences, and a
potential strategy for achieving the perfect genome in a cost effective
manner.

Strategy -

<http://www.frontiersin.org/files/Articles/120818/fgene-05-00466-HTML/image_m/
fgene-05-00466-g001.jpg>

> FIGURE 1. The concept of read co-barcoding for advanced whole genome
sequencing (WGS). All four critical requirements are depicted. (1) A genomic
library is prepared from long DNA (e.g., 30300 kb) representing 10 or more
cells. Multiple staggered long DNA fragments for each genomic region are
generated as a result of random fragmenting during cell lysis (three fragments
depicted under each parental chromosome). In the co-barcoded read libraries
these redundant long fragments allow variant phasing, a more accurate assembly
of the genome, and ultimately de novo assembly. In this example a pair of long
proximate repeat elements, longer than the read and mate-pair length, is shown
by the large gray boxes. A and C denote single base differences between copies
of these repeat elements. Long, overlapping, staggered genomic fragments allow
for the proper placement of these repeats in the final assembly by exclusive
linking of repeat members to surrounding unique sequences provided by the long
DNA fragments that start or end between repeats. (2) Sequence reads generated
from each long fragment (i.e., subfragments used to produce these reads) are
tagged (small colored curved lines) with the same barcode (co-barcoded). There
are many (usually 10s100s) of reads per long DNA fragment, most if not all
having the same barcode. Reads belonging to related (i.e., overlapped) long
fragments mostly have different barcodes. Consequently maternal (red) and
paternal (blue) fragments for a genomic region have different barcodes as
indicated by the distinct barcode numbers (253, 112, and X for mom, 27, 367,
and Y for dad). After MPS, barcodes are used to aggregate reads from the
original long fragment. Such read aggregation, even without sequence assembly
per long fragment, provides information for variant phasing and repeat
resolving when reads from overlapping long fragments, representing the same
chromosome, are used together in the assembly process. (3) Sequence reads must
cover >30% and preferably the majority of bases in each long fragment.
Consecutive continuous reads (depicted here) or overlapping mate-pair reads
(two shorter reads from the ends of the same subfragment) can provide the
needed coverage. Sequencing the majority of bases of each fragment with co-
barcoded reads links alleles in haplotypes as, on average, 10 or more
heterozygous sites occur per long DNA fragment. (4) The read or mate-pair
length is longer than the frequent dispersed repeats (e.g., Alu, depicted by
the small gray boxes) and are correctly assembled primarily using read level
data.

Cost mentioned in the paper - $200/genome

