---
title: Bowtie Alignment with and without Quality Score
tags: []
categories:
- blog
---
For new readers, easiest way to follow us is through our [twitter
feed](https://twitter.com/#!/homolog_us/). The feed is updated, whenever we
post a commentary here.
<!--more-->

This is a rather trivial point, but we somehow missed it in a calculation and
spent couple of hours debugging our codes. When you use Bowtie to align a
fastq file on to a reference genome, and also use Bowtie to align the
corresponding fasta file on the same reference genome, the results can be
different. The number of alignments for the fastq file are larger, because
Bowtie uses quality scores embedded in fastq file to align 5' ends of some
reads with erroneous 3' ends. The corresponding reads from fasta file cannot
be aligned, because fasta strips off all quality information.

We were mapping a huge RNAseq library on to a set of genes assembled by
Trinity, and it occurred to us that we could speed up the process by
aggregating many copies of the same read into one. Typically, transcriptome
libraries have hundreds or thousands of identical reads coming from highly
expressed genes, and it does not make sense to find alignments of those same
reads thousand times on to a reference genome.

When we performed the alignment in above manner, the results came out to be
surprising. About 92% of reads from the original fastq file matched the
reference sequence, but only 81% of reads from the condensed fasta file
matched the reference. When we say 81%, we do adjust for multiple copies of
removed reads in our counting. After spending some time chasing the wrong
alleys, we finally figured out that the difference came from reads with poor-
quality 3' ends that were properly mapped from fastq file, but remained
unmapped for fasta format.

Quoting from the [Bowtie paper](http://genomebiology.com/2009/10/3/R25) \-

> The first 28 bases on the high-quality end of the read are termed the
'seed'. The seed consists of two halves: the 14 bp on the high-quality end
(usually the 5' end) and the 14 bp on the low-quality end, termed the 'hi-
half' and the 'lo-half', respectively. Assuming the default policy (two
mismatches permitted in the seed), a reportable alignment will fall into one
of four cases: no mismatches in seed (case 1); no mismatches in hi-half, one
or two mismatches in lo-half (case 2); no mismatches in lo-half, one or two
mismatches in hi-half (case 3); and one mismatch in hi-half, one mismatch in
lo-half (case 4).

All cases allow any number of mismatches in the nonseed part of the read and
all cases are also subject to the quality distance constraint.

The Bowtie algorithm consists of three phases that alternate between using the
forward and mirror indices, as illustrated in Figure 3. Phase 1 uses the
mirror index and invokes the aligner to find alignments for cases 1 and 2.
Phases 2 and 3 cooperate to find alignments for case 3: Phase 2 finds partial
alignments with mismatches only in the hi-half and phase 3 attempts to extend
those partial alignments into full alignments. Finally, phase 3 invokes the
aligner to find alignments for case 4.

Bowtie can be forced to ignore quality values by giving options like 'bowtie
-v 2'.

