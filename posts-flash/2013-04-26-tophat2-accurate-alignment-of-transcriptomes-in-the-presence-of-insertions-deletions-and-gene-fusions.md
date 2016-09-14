---
title: 'TopHat2: Accurate Alignment of Transcriptomes in the Presence of Insertions,
  Deletions and Gene Fusions'
tags: []
categories:
- blog
---
[Link from Genome
Biology](http://genomebiology.com/content/pdf/gb-2013-14-4-r36.pdf) h/t:
@genetics_blog
<!--more-->

**The problem:**

> More importantly for the alignment problem, ~20% of junction-spanning reads
extend 10 bp or less into one of the exons they span. These small anchors make
it extremely difficult for alignment software to map reads accurately,
particularly if the algorithm relies (as most do) on an initial mapping of
fixed-length k-mers to the genome. This initial mapping, using exact matches
of k-mers, is critical for narrowing down the search space into small local
regions where a read is likely to align. If a read only extends a few bases
into one of two adjacent exons, then it often happens that the read will align
equally well, but incorrectly, with the sequence of the intervening intron.
For example, as illustrated in Figure 1, suppose that read r spans exons e1
and e2, extending only 4 bases into e2. Suppose also that that e2 begins with
GTXX, and the intervening intron also begins with GTXX, where X stands for any
of A, G, C, and T. Then r might align perfectly to e1 and the first 4 bases of
the intron, and the alignment algorithm will fail to find the spliced
alignment of r.

**Solution:**

> In order to handle this problem, TopHat2 uses a two-step procedure. First,
similar to TopHat1 [4], it detects potential splice sites for introns
(detailed further in Materials and methods). It uses these candidate splice
sites to align multi-exon spanning reads properly in a subsequent step. Some
RNA-seq aligners, including GSNAP [5], RUM [6], and STAR [7], map reads
independently of the alignments of other reads, which may explain their lower
sensitivity for these spliced reads (see Results and discussion). MapSplice
[8] uses a two-step approach similar to TopHat2.

When you have good annotation, such as in human genome, TopHat2 can also use
the annotations "during its initial mapping phase, which produces significant
gains in sensitivity and accuracy".

Finally, color space is included !

The paper has many good comparisons with other alignment programs. For
example,

> GSNAP, RUM, and STAR have particular difficulty aligning short-anchored
reads, only aligning 26%, 8.6%, and 3.5%, respectively. MapSplice does
considerably better, aligning 75.6% of these reads. By contrast, TopHat2
aligns 93.7% of the short-anchored reads using Bowtie1 as its main aligner
(Table 1).

Overall TopHat2 is a big improvement over a program that was excellent itself.

