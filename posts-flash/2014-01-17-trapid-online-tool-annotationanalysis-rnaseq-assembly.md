---
title: 'TRAPID: Online Tool for Annotation&#47;Analysis of RNAseq Assembly'
tags: []
categories:
- rnaseq
---
What is worse than getting your paper rejected? It is to get the paper
published in late December, when everyone is away for vacation. The TRAPID
paper by Michiel van Bel and colleagues had such misfortune, but we believe
the labs trying to annotate and analyze RNAseq data will find it helpful. The
groups of Yves Van de Peer and Klaas Vandepoele published many other useful
bioinformatics tools in the past.
<!--more-->

[TRAPID: an efficient online tool for the functional and comparative analysis
of de novo RNA-Seq transcriptomes](http://genomebiology.com/2013/14/12/R134)

> Transcriptome analysis through next-generation sequencing technologies
allows the generation of detailed gene catalogs for non-model species, at the
cost of new challenges with regards to computational requirements and
bioinformatics expertise. Here, we present TRAPID, an online tool for the fast
and efficient processing of assembled RNA-Seq transcriptome data, developed to
mitigate these challenges. TRAPID offers high-throughput open reading frame
detection, frameshift correction and includes a functional, comparative and
phylogenetic toolbox, making use of 175 reference proteomes. Benchmarking and
comparison against state-of-the-art transcript analysis tools reveals the
efficiency and unique features of the TRAPID system. TRAPID is freely
available at http://bioinformatics.psb.ugent.be/webtools/trapid/

We have been studying their implementation in detail over the last week and
find many attractive features. It is designed with efficiency in mind.

(i) For comparative analysis, they start with pre-computed gene families in
[PLAZA (for plants)](http://bioinformatics.psb.ugent.be/plaza/) and [OrthoMCL-
DB (eukaryotes)](http://orthomcl.org/orthomcl/).

(ii) Gene search is done using
[RAPSearch2](http://www.ncbi.nlm.nih.gov/pubmed/22039206) instead of NCBI NR
BLAST or Interproscan.

> In a previous work, we developed RAPSearch, an algorithm that achieved a
~20-90-fold speedup relative to BLAST while still achieving similar levels of
sensitivity for short protein fragments derived from NGS data. RAPSearch,
however, requires a substantial memory footprint to identify alignment seeds,
due to its use of a suffix array data structure. Here we present RAPSearch2, a
new memory-efficient implementation of the RAPSearch algorithm that uses a
collision-free hash table to index a similarity search database. The
utilization of an optimized data structure further speeds up the similarity
search-another 2-3 times. We also implemented multi-threading in RAPSearch2,
and the multi-thread modes achieve significant acceleration (e.g. 3.5X for
4-thread mode). RAPSearch2 requires up to 2G memory when running in single
thread mode, or up to 3.5G memory when running in 4-thread mode.

(iii) Global alignment is done using MUSCLE and tree construction is done by
FastTree/PhyML.

(iv) All those packages are integrated in a CakePHP framework and can be
[downloaded from github](http://bioinformatics.psb.ugent.be/webtools/trapid/).

![TRAPID](http://genomebiology.com/content/figures/gb-2013-14-12-r134-1.jpg)

> Schematic overview of the TRAPID pipeline. The TRAPID pipeline consists of
two separate steps. The first one is a non-interactive processing step, during
which all transcripts are assigned to gene families using a RAPSearch2
similarity search, followed by functional annotation transfer and meta-
annotation assignment. The second step is interactive and directly commanded
through the website interface. Here, the user has the ability to analyze his
data using functional enrichment analyses, multiple sequence alignments, and
phylogenetic trees.

Enjoy !

\------------------------------------------

Edit.

Readers may find the following post relevant.

[AfterParty a Promising Post Processing Tool for Transcriptome
Data](http://www.homolog.us/blogs/blog/2013/10/23/afterparty-promising-post-
processing-tool-transcriptome-data/)

> afterPartys main use case scenario is one in which a working biologist has
generated a large volume of transcribed sequence data and wishes to turn it
into a useful resource that has some durability. By reducing the effort,
bioinformatics skills, and computational resources needed to annotate and
publish a transcriptome, afterParty will facilitate the annotation and sharing
of sequence data that would otherwise remain unavailable. A typical metazoan
transcriptome containing several tens of thousands of contigs can be annotated
in a few minutes of interactive time and a few days of computational time.

