---
title: The March of Pseudoalignment - Two Papers
tags: []
categories:
- blog
---
"Pseudoalignment" means aligning the reads on a reference based on minimal
sampling of k-mers from the reads. This, coupled with de Bruijn graph
representation of the reference, has become a powerful lightweight method for
RNAseq analysis ([Kallisto](http://www.homolog.us/blogs/blog/2015/07/10/will-i
-use-kallisto-definitely-most-likely-and-never/), Salmon) and now
metagenomics. Readers may enjoy the following papers from two top groups
working on this approach.
<!--more-->

Rob Patro and colleagues -

[RapMap: A Rapid, Sensitive and Accurate Tool for Mapping RNA-seq Reads to
Transcriptomes](http://biorxiv.org/content/early/2015/10/22/029652)

> Motivation: The alignment of sequencing reads to a transcriptome is a common
and important step in many RNA-seq analysis tasks. When aligning RNA-seq reads
directly to a transcriptome (as is common in the de novo setting or when a
trusted reference annotation is available), care must be taken to report the
potentially large number of multi-mapping locations per read. This can pose a
substantial computational burden for existing aligners, and can considerably
slow downstream analysis. Results: We introduce a novel algorithm, quasi-
mappin, for mapping sequencing reads to a transcriptome. By attempting only to
report the potential loci of origin of a sequencing read, and not the base-to-
base alignment by which it derives from the reference, RapMap --- the tool
implementing this quasi-mappin algorithm --- is capable of mapping sequencing
reads to a target transcriptome substantially faster than existing alignment
tools. The quasi-mapping algorithm itself uses several efficient data
structures and takes advantage of the special structure of shared sequence
prevalent in transcriptomes to rapidly provide highly-accurate mapping
information. Availability: RapMap is implemented in C++11 and is available as
open-source software, under GPL v3, at https://github.com/COMBINE-lab/RapMap.

Lior Pachter and colleagues -

[Pseudoalignment for metagenomic read
assignment](http://arxiv.org/abs/1510.07371)

> We explore connections between metagenomic read assignment and the
quantification of transcripts from RNA-Seq data. In particular, we show that
the recent idea of pseudoalignment introduced in the RNA-Seq context is
suitable in the metagenomics setting. When coupled with the Expectation-
Maximization (EM) algorithm, reads can be assigned far more accurately and
quickly than is currently possible with state of the art software.

Readers are also encouraged to read Lior Pachter's blog post -

[Straining metagenomics](https://liorpachter.wordpress.com/2015/10/27
/straining-metagenomics/)

> In response to the development of reference-based bioinformatics
possibilities for metagenomics, about three years ago my student Lorian
Schaeffer started looking at the suitability of RNA-Seq tools for metagenomic
read assignment. Although the metagenomic and RNA-Seq assignment problems are
conceptually similar and methodologically related, there are various technical
issues involved in applying RNA-Seq tools in the metagenomic setting (e.g. the
need to carefully account for taxonomy in the metagenomics setting). After
developing the computational infrastructure to benchmark RNA-Seq programs in
the metagenomic setting, she proceeded to evaluate the accuracy of eXpress, a
streaming algorithm for RNA-Seq quantification. Although the quantification of
eXpress was specifically designed to be suitable for large numbers of reads,
the program requires read alignments to a reference transcriptome (or in
Lorians experiments a genome) database. In the metagenomic setting realistic
databases are huge, and she found that it took days just to map the reads.
Nevertheless, her initial benchmarks revealed that eXpress was significantly
more accurate than the available metagenomic read assignment tools of the
time.

When Kraken (Wood and Salzberg 2014), and later CLARK (Ounit et al. 2015) were
published in 2014 and 2015 respectively, we took note because by circumventing
the alignment step they dramatically altered the tractability of metagenomic
read assignment. In parallel, in my group, Nicolas Bray and later Pll Melsted
and Harold Pimentel were developing what is now kallisto (Bray et al. 2015).
Like Kraken, kallisto avoided the need for aligning reads, but with the
introduction of the concept of pseudoalignment, allowed for accurate read
assignments based on joint analysis of exact k-mer matches. What we showed
earlier this year is that unlike nave k-mer based approaches to
quantification, kallisto is as accurate as eXpress and other read alignment
based quantification tools, and this observation led Lorian to immediately
proceed to benchmark it on metagenomic data. The result of her work was just
posted as a preprint:

Lorian Schaeffer, Harold Pimentel, Nicolas Bray, Pll Melsted and Lior Pachter,
Pseudoalignment for metagenomic read assignment, arXiv 1510.07371, 2015.

With this paper we demonstrate a technology transfer from RNA-Seq
bioinformatics to metagenomics, one that achieves dramatic improvements in
read assignment accuracy in the metagenomics setting. The main result of her
work is Table 1 in our preprint:

