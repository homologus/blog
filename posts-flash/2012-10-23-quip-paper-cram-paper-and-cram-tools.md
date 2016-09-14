---
title: Quip paper, CRAM paper and CRAM Tools
tags: []
categories:
- blog
---
When we [wrote earlier about Quip compression
algorithm](http://www.homolog.us/blogs/2012/07/19/quip-minia-slimgene-and-
titus-browns-paper-on-scaling-metagenome/), Quip paper was still unpublished
(i.e. in a journal), although it was readily available from author's website.
The paper is now [published in
NAR](http://nar.oxfordjournals.org/content/early/2012/08/14/nar.gks754.full)
and readers may take a look for additional details.
<!--more-->

Here is the most important innovation -

> To complement the reference-based approach, we developed an assembly-based
approach which offers some of the advantages of reference-based compression,
but requires no external sequence database and produces files which are
entirely self-contained. We use the first (by default) 2.5 million reads to
assemble contigs which are then used in place of a reference sequence database
to encode aligned reads compactly as positions.

Once contigs are assembled, read sequences are aligned using a simple seed and
extend method: 12-mer seeds are matched using a hash table, and candidate
alignments are evaluated using Hamming distance.

The assembly was done using a 'counting Bloom filter' data structure -

> The Bloom filter is generalized in the counting Bloom filter, in which an
arbitrary count can be associated with each element (12). A very similar data
structure, the CountMin Sketch, is described by Cormode and Muthukrishnan
(13), which was arrived at independently of the prior Bloom filter research.
Bonomi et al. (14) subsequently described the d-left counting Bloom filter
(dlCBF), a refinement of the counting Bloom filter requiring significantly
less space to achieve the same false positive rate.

We base our assembler on a realization of the dlCBF. Since we use a
probabilistic data structure, k-mers are occasionally reported to have
incorrect (inflated) counts. The assembly can be made less accurate by these
incorrect counts, however a poor assembly only results in slightly increasing
the compression ratio. Compression remains lossless regardless of the assembly
quality, and in practice collisions in the dlCBF occur at a very low rate
(this is explored in the Results section).

Given a probabilistic de Bruijn graph, we assemble contigs using a very simple
greedy approach. A read sequence is used as a seed and extended on both ends
one nucleotide at a time by repeatedly finding the most abundant k-mer that
overlaps the end of the contig by k ? 1 bases. More sophisticated heuristics
have been developed, but we choose to focus on efficiency, sacrificing a
degree of accuracy.

In the context of reference-based compression, we encourage the readers to
take a look at the [2011 CRAM
paper](http://genome.cshlp.org/content/21/5/734.long) and [CRAM
tools](http://www.ebi.ac.uk/ena/about/cram_toolkit) from EBI.

> For every read we store its starting position with respect to the reference,
its strand, and a flag indicating whether the read matches to the reference
perfectly. Positions are relative encoded (i.e., the difference between
successive positions is stored rather than the absolute value) and stored as a
Golomb code, resulting in a variable length code. Strand and match flags
require one bit each. In the case of a nonperfect match, we store a list of
variations. Every variation is stored as its position on the read, the
variation type (substitution, insertion, deletion), and additional information
(the base change in the case of a substitution, the inserted bases, or the
length of the deletion). Again, positions are relative and Golomb encoded. The
variation type (substitution, insertion, or deletion) is encoded in 1 or 2
bits.......For quality budgets, where identical bases are present we store a
bit indicating whether the base is the same as the reference, optionally
followed by an encoding of the change of base as explained before. Inserted
bases are encoded in 2 or 3 bits (in truncated binary encoding, similar to the
variation type). Deletion lengths are currently Gamma encoded (Elias 1975).

More details [here](http://genome.cshlp.org/content/21/5/734.long).

