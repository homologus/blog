---
title: Top Ten Genomes - (ix) Pacific oyster
tags: []
categories:
- blog
---
Some genomes are so difficult to assemble, they are remembered by scientists
trying to assemble them for all their life. Ruibang Luo at BGI possibly had
such a shocking experience with pacific oyster, because it was the first
genome he mentioned after my talk at Hong Kong University. Baylor genome
center experienced similar difficulties with the urchin genome and Jeramiah
Smith did not find the lamprey genome any easier.
<!--more-->

High degree of heterozygosity is the common theme among those three genomes.
Almost all assembly programs assume two copies of chromosomes to be identical.
Therefore, when someone tries to run an existing program like SOAPdenovo on
pacific oyster or lamprey, he comes up with very tiny contigs fragmented by
'bubbles' (an algorithmic term for de Bruijn graph-based assemblers).

Dipspades module within SPAdes is one of the few existing programs, which can
handle such assemblies algorithmically. However, SPAdes assembler cannot scale
well for large assemblies yet. The other option is to get a Pacbio sequencing
instrument, which appears to be the direction chosen by BGI.

[BGI Adopts Single Molecule, Real-Time Sequencing from Pacific Biosciences](ht
tp://investor.pacificbiosciences.com/releasedetail.cfm?ReleaseID=910410)

Pacific oyster genome wins our nomination as a representative of highly
polymorphic genome. Apart from being a nightmare for bioinformaticians, such
genomes also raise interesting biological questions, such as how do those
organisms manage to survive with such rapidly changing genomes. If [80% of
genomes were functional](http://www.evolutionnews.org/2012/09/junk_no_more_en_
1064001.html), one of those changes will hit a functional region very soon and
make the organism defective. Therefore, it is likely that the organisms will
head extinction much more rapidly than those with stable genomes.

