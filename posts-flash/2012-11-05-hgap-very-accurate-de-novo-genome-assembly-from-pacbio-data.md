---
title: HGAp - Very Accurate de novo Genome Assembly from PacBio Data
tags: []
categories:
- blog
---
In its website, [PacBio posted a new algorithm](http://www.smrtcommunity.com/S
hare/Code?id=a1q70000000H2qRAAS&strRecordTypeName=Code) for <del>predicting
its stock price</del> de novo genome assembly with 99.99% accuracy.
<!--more-->

>

**Background**

Previous approaches for pure PacBio de novo assembly, like pacBioToCA and
RS_Allora_Assembly_EC, require two libraries: typically one 10 kb library for
continuous long reads (CLR), and one 1 kb library for circular consensus
sequencing (CCS) reads. The CCS reads are aligned against the long reads in
order to take a consensus and generate very long, highly accurate reads. In
addition to requiring two library preps, the CLR plus CCS approach can require
many SMRT Cells to generate sufficient coverage of CCS data.

HGAp simplifies the sample preparation process by requiring only a single
library prep, which reduces by half the input DNA required. HGAp also reduces
the number of SMRT Cells required by using single-pass reads rather than CCS.
For example, assemblies using HGAp may use 1/4 to 1/2 as many SMRT Cells as
assemblies using CCS. As a result, microbial genome assembly can be performed
with less input DNA, with less sample preparation, at lower cost, and in less
time. Larger genomes become more feasible because the useful throughput
increases.

**Methods**

HGAp consists of a series of well-defined steps:

Generate at least 60x coverage (ideally at least 100x coverage) of your target
genome using a long insert library with 90 or 120 minute movies

Choose a subread length threshold such that subreads above the threshold
provide about 20x coverage of the genome.

Filter the base files using the subread length threshold. The file of long
subreads constitutes the "seeding reads".

Use BLASR to map all data against the seeding reads. Use BLASR's "-m 4"
option. Set the "bestn" to allow multiple mapped locations; a value in the
range of 5 to 12 seems to work well for 20x coverage.

Process the mapped data, trimming to the boundaries of the seeding reads minus
100 bp.

Take a consensus of the pre-assembled reads using a partial order alignment or
other highly accurate method.

Feed the pre-assembled reads into an overlap-layout-consensus assembler that
can handle very long reads.

Take the output of the assembler, and treat it as a reference genome. Map all
raw data against it using BLASR. Trim at the contig boundaries and take the
consensus using Quiver to "polish" the assembly and remove errors.

Also, we updated [our previous commentary on
PacBio](http://www.homolog.us/blogs/2012/11/05/a-simulator-for-pacbio-reads/)
to include an interesting paper from Eric Schadt's group recently published in
Genome Research. We thank Jason Chin and his [personal twitter feed
infoecho](https://twitter.com/infoecho) (check disclaimer in comment section)
for teaching us about many aspects of PacBio technology.

