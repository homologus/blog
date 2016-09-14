---
title: FASTG - A New Format for Representing Sequences
tags: []
categories:
- blog
---
While discussing about a newly assembled genome with several collaborators few
months back, we felt that there was a huge gap between what we
(bioinformaticians working on assembly) thought of a genome and how our
biologist collaborators perceived of a genome. To us, the genome was an
unfinished piece of work like the first draft of a paper. To biologists, the
genome was a paper ready to be submitted, or a paper already in print. That
was understandable, because our colleagues were more familiar with human and
mouse genomes, which were already of high quality.
<!--more-->

What we found difficult to communicate was that some part of the genome were
of high quality and trustworthy, while some other parts were intelligent
guesswork. The users viewed the genome as a flat FASTA file, and therefore
assumed that either everything was equally good or everything was bad. Our
only other option was to fragment the genome into one million reliable tiny
pieces, but that would have frustrated the users even more. In fact, the issue
of variable assembly quality is not only an issue in communication between
bioinformaticians and non-bioinformaticians, similar questions arise, when two
assemblers try to communicate to improve on assemblies completed by each
other.

A new format called FASTG is created to address the above issues. FASTG is
expected provide a realistic view of an assembled genome instead of presenting
it as a long chain of nucleotides. [From their
website](http://fastg.sourceforge.net/):

> FASTG is a format for faithfully representing genome assemblies in the face
of allelic polymorphism and assembly uncertainty. It is called FASTG, like
FASTA, but the G stands for graph.

Currently genome assemblies are represented linearly, as sequences of bases,
recorded in FASTA files. Since chromosomes are in fact linear or circular,
this makes sense, so long as one has complete knowledge of the genome.
However, almost all assemblies contain errors and omissions, which can result
in incorrect biological inferences. Moreover, in most cases these assemblies
do not represent polymorphism at all.

Today, using high-coverage data, assembly algorithms 'see' almost all bases of
the genome. Thus errors in the assemblies result primarily from defects in the
algorithms and defects in assembly representation. Indeed, where a particular
locus in an assembly is wrong, it is generally the case that the assembly
algorithm could have prevented error by emitting an ambiguous call. However,
such ambiguities are precluded by the current linear representation.
Similarly, complex polymorphisms cannot be easily represented either and
simple polymorphisms must be captured in a supporting file.

Just as physical measurements come with error bars, so should genome
assemblies come with structures that capture the uncertainties in our
knowledge. At its heart it is FASTA thus allowing existing tools to run and
providing coordinates that facilitate computation. On top of this are global
and local layers of markup.

Here is an example of FASTA format:

`

>chr1:chr1;

ACGANNNNNCAGGCTATACG

>chr2;

ACATACGCATATATATATATATATATATTCAGGCAGGAC

`

Similar sequence in FASTG format:

`

#FASTG:begin;

#FASTG:version=1.0:assembly_name="tiny example";

>chr1:chr1;

ACGANNNNN[5:gap:size=(5,4..6)]CAGGC[1:alt:allele|C,G]TATACG

>chr2;4

ACATACGCATATATATATATATATATAT[20:tandem:size=(10,8..12)|AT]TCAGGCA[1:alt|A,T,TT
]GGAC

#FASTG:end;`

