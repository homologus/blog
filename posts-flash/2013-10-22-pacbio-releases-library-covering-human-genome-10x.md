---
title: PacBio Achieves 500Mb&#47;SMRT Cell Throughput in Newly Released Human Data
tags: []
categories:
- blog
---
[From PacBio blog](http://blog.pacificbiosciences.com/2013/10/data-release-
long-read-shotgun.html):
<!--more-->

>

In collaboration with Evan Eichler (Howard Hughes Medical Institute,
University of Washington), we sequenced CHM1TERT, a well-studied cell line
derived from a complete hydatidiform mole (CHM). A hydatidiform mole is
defined as a pregnancy with no embryo and clinically presents in approximately
1 in 1,500 pregnant women in North America. The CHM cells have a diploid
genome, typically XX, that is a result of replication of a haploid paternal
(sperm) genome. Through the corresponding absence of allelic variation, this
sample has been used to generate a haploid reference genome sequence, and many
associated resources are available, including physical maps, genotypes
(iSCAN), and a large-insert BAC library (CHORI-17). It is also one of the
targets for the production of a higher quality platinum genome assembly.

The stats are quite fascinating. They have 66 SMRT cells producing
32,559,803,198 bases of post-filtered nucleotides. Therefore, on average, each
SMRT cell produced 493Mb of sequences. A few days back, [we asked about the
typical throughput of PacBio machines](http://seqanswers.com/forums/showthread
.php?p=118796&posted=1#post118796) at seqanswers. Lex Nederbragt and Genomax
reported 150-300 Mb with pre-P4 chemistry and only one exceptional case of 730
Mb with P4 chemistry. On the other hand, 500 Mb per SMRT cell appears to be
common with P5-C3 chemistry here. Other stats:

>

Average read length: 8,849 bp

Half of sequenced bases in reads greater than: 10,985 bp

5% of sequenced DNA inserts longer than: 18,060 bp

Longest DNA insert sequenced: 41,460 bp

PacBio RS II instrument time for sequencing: 10 days

Their blog post has informative charts on read size distribution and one
example of a 114.2 kb deletion in the human genome !!!

![](http://2.bp.blogspot.com/-gLhDW6gCJSw/UmXU9tvQpKI/AAAAAAAAAGY/cENOsK1cV3A/
s400/graph3.png)

We tried to download the read libraries, but had no luck. Either everyone from
ASHG is clicking on the same URL, or the URL given to us by PacBio is
incorrect. We will post our own analysis, when the ASHG crowd stops clicking
on the link :)

