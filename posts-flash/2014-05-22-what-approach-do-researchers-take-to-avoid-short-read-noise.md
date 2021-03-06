---
title: 'What Approach Do Researchers Take to Avoid ''Short Read'' Noise? '
tags: []
categories:
- blog
---
[In a post last year](End of Short-Read Era?  \(Part I\)), we argued that the
'clean' short reads are noisy due to their short length, and that 'noise'
manifests in the higher stages of analysis. A newly published Nature paper
("[The ctenophore genome and the evolutionary origins of neural systems](http:
//www.nature.com/nature/journal/vaop/ncurrent/full/nature13400.html
#supplementary-information)") is a good example of the types of precautions
researchers take to make sure their major claims are not artifacts of short-
read noise.
<!--more-->

Right after reading the abstract, we realized that papers like above, which
derive their conclusions from genome comparison, face the difficulty that it
is hard to rule out assembly artifacts. For example, how can one be absolutely
sure that a gene declared missing from the genome of the organism is not
missing due to improper assembly?

The authors used two strategies to properly back their claims. First, they
added extensive amount of transcriptome data using every kind of sequencing
technology (454, Illumina, Ion Torrent). The transcriptome data have added
benefit of showing dynamic information not available from genome only. In our
research, we always encourage our collaborators to mix both genome and
transcriptome information.

The second strategy is to use every kind of genome assembler (SOAPdenovo,
ABySS, Velvet) to assemble the genomic reads, doing gene prediction in all
three assemblies and then merging three genomes and RNAseq together into one
assembly. Here is a subset of the method section -

> The Pleurobrachia bachei draft genome was assembled using a custom approach
designed to leverage the individual strengths of three popular de novo
assembly packages and strategies: Velvet3 (described in S2.2.1), SOAPdenovo4
(described in S2.2.2), and pseudo-454 hybrid assembly with ABySS5 (described
in S2.2.3). Input data sets for each de novo assembly were the 454 and
Illumina reads (Supplementary Tables 1S-3S). Contribution of non-redundant
scaffolds above 2kb by each of the individual de novo assemblies to the P.
bachei draft genome version 1.0 was decided as described in S2.2.4.

Briefly, genes were predicted in each of the three sets of genomic scaffolds
using Augustus version 2.5.56, initially trained on Amphimedon queenslandica,
then using several hundred Pleurorachia bachei genes from RNA-seq profiling
and about one hundred full-length genes manually cloned over the course of the
project in the Moroz laboratory. The three obtained sets of gene models were
then aligned against themselves with blastp to remove intra-assembly
redundancy. The resulting non-redundant lists were then pairwise-aligned to
each other to remove inter-assembly redundancy. Scaffolds from each assembly
that contributed a non-redundant gene model were included in the initial draft
assembly of the genome (21,982 scaffolds containing 156,146,497 bp). Draft
version 1.1 of the genome was produced by screening and removing contamination
from prokaryotic sequences as described in the S2.3. Full summary statistics
for the draft genome of P. bachei are presented in Supplementary Table 5S.

The entire methods section shows a lot of heavy-duty bioinformatics work done
to get the genome and genes right, and is necessary to avoid 'short read
noise'. If, in addition to multiple assemblers, they also looked at multiple
k-mer values, that would mean a lot of assemblies done to finally arrive at
the right combination.

The amount of raw reads generated by this paper is incredible and we believe
curious scientists will find many more interesting information from their data
in years to come. Is it time to declare moratorium on generating many more new
sequencing libraries and see what has been already out there?

