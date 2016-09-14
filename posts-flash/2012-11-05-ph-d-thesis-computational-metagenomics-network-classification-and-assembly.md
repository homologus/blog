---
title: 'Ph. D. Thesis: Computational Metagenomics: Network, Classification and Assembly'
tags: []
categories:
- blog
---
Readers will find the Ph. D. thesis of Bo Liu very useful (ht Jonathan Eisen).
The research was done under the supervision of Mihai Pop at University of
Maryland.
<!--more-->

[Abstract](http://drum.lib.umd.edu/handle/1903/13278) \-

> Due to the rapid advance of DNA sequencing technologies in recent 10 years,
large amounts of short DNA reads can be obtained quickly and cheaply. For
example, a single Illumina HiSeq machine can produce several terabytes of data
sets within a week. Metagenomics is a new scientific field that involves the
analysis of genomic DNA sequences obtained directly from the environment,
enabling studies of novel microbial systems. Metagenomics was made possible
from high-throughput sequencing technologies. The analysis of the resulting
data requires sophisticated computational analyses and data mining. In
clinical settings, a fundamental goal of metagenomics is to help people
diagnose and cure disease in clinical settings. One major bottleneck so far is
how to analyze the huge noisy data sets quickly and precisely. My PhD research
focuses on developing algorithms and tools to tackle these challenging and
interesting computational problems. From the functional perspective, a
metagenomic sample can be represented as a weighted metabolic network, in
which the nodes are molecules, edges are enzymes encoded by genes, and the
weights can be considered as the number of organisms providing the functions.
One goal of functional comparison between metagenomic samples is to find
differentially abundant metabolic subnetworks between two groups under
comparison. We have developed a statistical network analysis tool - MetaPath,
which uses a greedy search algorithm to find maximum weight subnetwork and a
nonparametric permutation test to measure the statistical significance. Unlike
previous approaches, MetaPath explicitly searches for significant subnetwork
in the global network, enabling us to detect signatures at a finer level. In
addition, we developed statistical methods that take into account the topology
of the network when testing the significance of the subnetworks. Another
computational problem involves classifying anonymous DNA sequences obtained
from metagenomic samples. There are several challenges here: (1) The
classification labels follow a hierarchical tree structure, in which the
leaves are most specific, and the internal nodes are more general. How can we
classify novel sequences that do not belong to leaf categories (species) but
belong to internal groups (e.g., phylum)? (2) For each classification how can
we compute a confidence score, such that the users have a tradeoff between
sensitivity and specificity? (3) How can we analyze billions of data items
quickly? We have developed a novel hierarchical classifier (MetaPhyler) for
the classification of anonymous DNA reads. Through simulation, MetaPhyler
models the distribution of pairwise similarities within different hierarchical
groups with nonparametric density estimation. The confidence score is computed
by the ratio of likelihood function. For a query DNA sequence with arbitrary
length, its similarity can be calculated through linear approximation. Through
benchmark comparison, we have shown that MetaPhyler is significantly faster
and more accurate than previous tools. DNA sequencing machines can only
produce very short strings (e.g., 100bp) relative to the size of a genome
(e.g., a typical bacterial genome is 5Mbp). One of the most challenging
computational tasks is the assembly of millions of short reads into longer
contigs, which are used as the basis of subsequent computational analyses. In
this project, we have developed a comparative metagenomic assembler
(MetaCompass), which utilizes the genomes that have already been sequenced
previously, and produces long contigs through read mapping (alignment) and
assembly. Given the availability of thousands of existing bacteria genomes,
for a particular sample, MetaCompass first chooses a best subset as reference
based on the taxonomic composition. Then, the reads are aligned against these
genomes using MUMmer-map or Bowtie2. Afterwards, we use a greedy algorithm of
the minimum set-covering problem to build long contigs, and the consensus
sequences are computed by the majority rule. We also propose an iterative
approach to improve the performance. Finally, MetaCompass has been
successfully evaluated and tested on over 20 terabytes of metagenomic data
sets generated from the Human Microbiome Project. In addition, to facilitate
the identification and characterization of antibiotic resistance genes, we
have created Antibiotic Resistance Genes Database (ARDB), which provides a
centralized compendium of information on antibiotic resistance. Furthermore,
we have applied our tools to the analysis of a novel oral microbiome data set,
and have discovered interesting functional mechanisms and ecological changes
underlying the transition from health to periodontal disease of human mouth at
a system level.

Full thesis can be downloaded [from
here](http://drum.lib.umd.edu/bitstream/1903/13278/1/Liu_umd_0117E_13491.pdf).
Each chapter is also published as number of papers.

>

At the time of this writing, Chapters 2, 3, 4 and 5 have already been
published. Chapter 6 and an improved version of Chapter 2 are under
preparation for sub-

mission.

Chapter 2:

\- Bo Liu, Theodore Gibbons, Mohammadreza Ghodsi, Mihai Pop. MetaPhyler:
Taxonomic pro ling for metagenomic sequences. Proceedings of 2010 IEEE
Bioinformatics and Biomedicine:95-100.

\- Bo Liu, Theodore Gibbons, Mohammad Ghodsi, Todd Treangen, Mihai Pop.
Accurate and fast estimation of taxonomic pro les from metagenomic shotgun
sequences.BMC Genomics 2011, 12(Suppl 2):S4

\- Bo Liu, Mihai Pop. Training and classi cation of metagenomic sequences with
con dence score. In preparation.

Chapter 3:

\- Bo Liu, Mihai Pop. Identifying Di erentially Abundant Metabolic Pathways in
ii Metagenomic Datasets. Lect Notes Comput Sci 2010, 6053: 101-112

\- Bo Liu, Mihai Pop. MetaPath: identifying diff erentially abundant metabolic
pathways in metagenomic datasets. BMC Proceedings 2011, 5(Suppl 2):S9

Chapter 4:

\- Bo Liu, Mihai Pop. ARDB - Antibiotic Resistance Genes Database. Nucleic
Acids Res. 2009 Jan;37(Database issue):D443-7.

Chapter 5:

\- Bo Liu*, Lina Faller*, Niels Klitgord*, Varun Mazumdar*, Mohammad Ghodsi,
Daniel D. Sommer, Theodore R. Gibbons, Todd J. Treangen, Yi-Chien Chang, Shan
Li, O. Colin Stine, Hatice Hasturk, Simon Kasif, Daniel Segre, Mihai Pop,
Salomon

Amar. PLoS One 2012, 7(6):e37919.

Chapter 6:

\- Bo Liu, Mihai Pop. MetaCompass: comparative assembly of metagenomic
sequences. In preparation.

