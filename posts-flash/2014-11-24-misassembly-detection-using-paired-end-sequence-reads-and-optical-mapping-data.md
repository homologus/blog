---
title: Misassembly Detection using Paired-End Sequence Reads and Optical Mapping Data
tags: []
categories:
- blog
---
This [arxiv paper](http://arxiv-web3.library.cornell.edu/abs/1411.5890)
appears to be promising (h/t: @lexnederbragt). We are not sure whether having
optical map data is an absolute requirement. (Edit. Please see comment from
senior author).
<!--more-->

> A crucial problem in genome assembly is the discovery and correction of
misassembly errors in draft genomes. We develop a method that will enhance the
quality of draft genomes by identifying and removing misassembly errors using
paired short read sequence data and optical mapping data. We apply our method
to various assemblies of the loblolly pine and Francisella tularensis genomes.
Our results demonstrate that we detect more than 54% of extensively
misassembled contigs and more than 60% of locally misassembed contigs in an
assembly of Francisella tularensis, and between 31% and 100% of extensively
misassembled contigs and between 57% and 73% of locally misassembed contigs in
the assemblies of loblolly pine. MISSEQUEL can be downloaded at [this http
URL](http://www.cs.colostate.edu/seq/).

If you are wondering how it relates to other available tools, the following
section is helpful.

> Related Work. Both amosvalidate [31] and REAPR [32] are capable of
identifying and correcting misassembly errors. REAPR is designed to use both
short insert and long insert paired-end sequencing libraries, however, it can
operate with only one of these types of sequencing data. Amosvalidate, which
is included as part of the AMOS assembly package [33], was developed
speci^Lcally for first generation sequencing libraries [31]. iMetAMOS [34] is
an automated assembly pipeline that provides error correction and validation
of the assembly. It packages several open-source tools and provides annotated
assemblies that result from an ensemble of tools and assemblers. Currently, it
uses REAPR for misassembly error correction.

Many optical mapping tools exist and deserve mentioning, including AGORA [35],
SOMA [36], and Twin [30]. AGORA [35] uses the optical map information to
constrain de Bruijn graph construction with the aim of improving the resulting
assembly. SOMA [36] uses dynamic programming to align in silico digested
contigs to an optical map. Twin [30] is an index-based method for align-ing
contigs to an optical map. Due to its use of an index data structure it is
capable of aligning in silico digested contigs orders of magnitude faster than
competing methods. Xavier et al. [37] demonstrated misassembly errors in
bacterial genomes can be detected using proprietary software. Lastly, there
are special purpose tools that have some relation to misSEQuel in their
algorith-mic approach. Numerous assembly tools use a finishing process after
assembly, including Hapsem-bler [38], LOCAS [39], Meraculous [40], and the
\assisted assembly" algorithm [41]. Hapsembler [38] is a haplotype-specific
genome assembly toolkit that is designed for genomes that are highly-
polymorphic. Both RACA [42], and SCARPA [43] perform paired-end alignment to
the contigs as an initial step, and thus, are similar to our algorithm in that
respect.

\------------------------------------------------

The following program by Heng Li is also worth noting.

[Abreak: evaluating de novo assemblies](http://lh3.github.io/2014/07/07
/abreak-evaluating-de-novo-assemblies/)

> Abreak is a subcommand of htsbox, which is a little toy forked from on the
lite branch of htslib. It takes an assembly-to-reference alignment as input
and counts the number of alignment break points. An earlier version was used
in my fermi paper to measure the missassembly rate of human de novo
assemblies. A typical output looks like:

Number of unmapped contigs: 239

Total length of unmapped contigs: 54588

Number of alignments dropped due to excessive overlaps: 0

Mapped contig bases: 2933399461

Mapped N50: 6241

Number of break points: 102146

Number of Q10 break points longer than (0,100,200,500)bp:
(28719,7206,4644,3222)

Number of break points after patching gaps short than 500bp: 94298

Number of Q10 break points longer than (0,100,200,500)bp after gap patching:
(23326,5320,3369,2194)

