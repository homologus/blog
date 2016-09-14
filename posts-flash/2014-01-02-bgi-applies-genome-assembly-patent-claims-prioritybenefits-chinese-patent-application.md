---
title: BGI Applies for Genome Assembly Patent, Claims Priority&#47;Benefits from Chinese
  Patent Application
tags: []
categories:
- blog
---
Q1. What is a 'device' for assembly - a server?
<!--more-->

Q2. Is the Chinese Patent Application database maintained in Chinese language?

[Link](http://www.freepatentsonline.com/y2013/0345095.html) (h/t:
@assemblathon)

>

ABSTRACT

A method and an apparatus for genome assembly are provided. The method
comprises: filtering a short-fragment-sequence output from end sequencing of
an large insert-size library to remove unqualified sequence; aligning the
filtered short-fragment-sequence onto a reference genome sequence, wherein,
the filtered short-fragment-sequences comprise paired short-fragment-
sequences; sorting the paired short-fragment-sequence after alignment into
soap reads sequence, single reads sequence and unmap reads sequence based on
the aligning result, and counting the number of each sort of sequence;
calculating a distance between the paired soap reads on a fragment of the
reference genome sequence, wherein a pair of the paired soap reads can be
aligned onto a same fragment of the reference genome sequence; and counting a
distance distribution of each pair of soap reads on the reference genome
sequence; and assembling the genome sequence by using the paired single reads
upon the distance distribution meeting a requirement of a threshold, wherein a
pair of the paired single reads can be aligned onto two different fragments of
the reference genome sequence.

CLAIMS

What is claimed is:

1\. A method for genome assembly comprising: filtering a short-fragment-
sequence output from end sequencing of a large insert-size library to remove
unqualified sequences, the qualified sequences comprising filtered short-
fragment-sequences; aligning the filtered short-fragment-sequences to a
reference genome sequence, wherein the filtered short-fragment-sequences
comprise paired short-fragment-sequences; sorting the paired short-fragment-
sequences after alignment into soap reads sequences, single reads sequences,
and unmap reads sequences based on an aligning result, and counting the number
of each sort; calculating a distance between the paired soap reads on a
fragment of the reference genome sequence, wherein a pair of the paired soap
reads can be aligned onto a same fragment of the reference genome sequence;
and counting a distance distribution of each pair of soap reads on the
reference genome sequence; and assembling a genome sequence by using the
paired single reads upon the distance distribution meeting a requirement of a
threshold, wherein a pair of the paired single reads can be aligned onto two
different fragments of the reference genome sequence.

2\. The method according to claim 1, wherein before aligning the filtered
short-fragment-sequences to the reference genome sequence further comprises
the step of: intercepting the filtered short-fragment-sequences to short-
fragment-sequences with a preset length.

3\. The method according to claim 1, wherein the unqualified sequences
comprise at least one selected from a group consisting of: an exogenous
sequence, a short-fragment-sequence having a preset ratio of a number N bases,
a short-fragment-sequence comprising poly A, a short-fragment-sequence having
a preset ratio of a number of low-quality bases, a short-fragment-sequence
having a contaminant from adaptor, a short-fragment-sequence having an overlap
with its paired short-fragment-sequence, and a short-fragment-sequence
repeatedly detected.

4\. The method according to claim 1, wherein the soap reads sequence
comprises: paired reads can be uniquely aligned onto a same fragment of the
reference genome sequence, and paired reads can be non-uniquely aligned onto a
same fragment of the reference genome sequence, the step of calculating a
distance between the paired soap reads on a fragment of the reference genome
sequence, wherein a pair of the paired soap reads can be aligned onto a same
fragment of the reference genome sequence, further comprising: calculating the
distance between the paired soap reads uniquely aligned onto a same fragment
of the reference genome sequence.

5\. The method according to claim 1 further comprising constructing a large
insert-size-sequence library; and end-sequencing the large insert-size-
sequence library to obtain output short-fragment-sequences.

6\. An apparatus for genome assembly comprising: a sequence-filtering unit for
filtering a short-fragment-sequence output from end sequencing of a large
insert-size library to remove unqualified sequences; a sequence-aligning unit,
connected to the sequence-filtering unit, for aligning the filtered short-
fragment-sequences to a reference genome sequence, wherein the filtered short-
fragment-sequences comprise paired short-fragment-sequences; a sequence-
sorting unit, connected to the sequence-aligning unit, for sorting the paired
short-fragment-sequences after alignment into a soap reads sequence, a single
reads sequence, and an unmap reads sequence based on an aligning result, and
counting a number of each sort of sequences; a sequence-length-calculating
unit, connected to the sequence-sorting unit, for calculating a distance
between the paired soap reads on a fragment of the reference genome sequence,
wherein a pair of the paired soap reads can be aligned onto a same fragment of
the reference genome sequence, and counting a distance distribution of each
pair of soap reads on the reference genome sequence; and a sequence-assembling
unit, respectively connected to the sequence-sorting unit and the sequence-
length-calculating unit, for assembling the genome by using the paired single
reads upon the distance distribution meeting a requirement of a threshold,
wherein a pair of the paired single reads can be aligned onto two different
fragments of the reference genome sequence.

7\. The apparatus according to claim 6 further comprising: a sequence-
intercepting unit, respectively connected to the sequence-filtering unit and
the sequence-aligning unit, for intercepting the filtered short-fragment-
sequences to short-fragment-sequences with a preset length before aligning the
filtered short-fragment-sequence to the reference genome sequence.

8\. The apparatus according to claim 6, wherein the unqualified sequences
comprise at least one selected from a group consisting of: an exogenous
sequence, a short-fragment-sequence having a preset ratio of the number N
bases, a short-fragment-sequence comprising poly A, a short-fragment-sequence
having a preset ratio of the number of low-quality bases, a short-fragment-
sequence having a contaminant from adaptors, a short-fragment-sequence having
an overlap with its paired short-fragment-sequence, and a short-fragment-
sequence repeatedly detected.

9\. The apparatus according to claim 6, wherein the soap reads sequence
comprises: paired reads can be uniquely aligned onto a same fragment of the
reference genome sequence, and paired reads can be non-uniquely aligned onto a
same fragment of the reference genome sequence, wherein the sequence-length-
calculating unit further comprises: calculating the distance between the
paired soap reads uniquely aligned onto a same fragment of the reference
genome; counting the distance distribution of the each pair of unique soap
reads on the reference genome sequence; wherein the sequence-assembling unit
further comprises: assembling the genome by using the unique paired single
reads upon the distance distribution meeting a requirement of a threshold,
wherein a pair of the unique paired single reads can be uniquely aligned onto
two different fragments of the reference genome.

10\. The apparatus according to claim 6 further comprising: a sequence-
receiving unit, connected to the sequence-filtering unit, for receiving the
short-fragment-sequences after the step of end-sequencing the large insert-
size library.

......

**

This application claims the priority to and benefits from Chinese Patent
Application No. 201110049885.0 filed with the State Intellectual Property
Office, P. R. C. on Mar. 2, 2011, the content of which is incorporated herein
by reference in its entirety.**

FIELD

The present disclosure relates to the field of biological information
technology, particularly to a method of assembling a genome sequence and an
apparatus thereof.

BACKGROUND

While the throughput of sequencing is increasing, the cost of sequencing
decreases sharply with the emergence of next generation sequencing technology,
such as 454 (Roche), Solexa (Illumina) and SOLiD (ABI). The next-generation
sequencing technology has greatly promoted the development of Genomics. Whole
genome sequences of a large number species have been published, including the
personal genome of James Watson, the first Asian genome, and genomes of giant
panda and cucumber.

Each round of sequencing of a next generation sequencing instruments can
generate millions of short fragment sequences. Typically, subjecting a genome
to a completely sequenced needs multiple rounds of sequencing work, which
means that, in order to obtain a whole genome-wide map, millions or even
billions of short fragment sequences may need to be plotted, positioned, and
jointed.

Therefore, current method of genome assembly needs to be improved.

SUMMARY

The present disclosure is based on the following findings of the inventors:

At present, when using a next generation sequencing technology for sequencing,
the output can be all short fragment sequences having a length of about 25 by
to about 100 bp. These short-fragment-sequences are some parts of large-
fragments of a sample to be tested. Subjecting massive amounts of short-
fragment-sequences data obtained from sequencing for assembly and restoring to
large-fragment data for subsequent information analysis is a great challenge.
In the prior art, because the fragment-sequences output from sequencing can be
very short, the restoration of large-fragment data can need a large amount of
calculation.

At the same time, the indicator of fragment-length N50 as a measurement of
genome quality can also be restricted with the length of inserted fragment for
constructing a library in an experiment. (N50 refers to a length which is
equivalent to 50% of overall length, obtained by putting and adding all
assembled sequences in a descending order. Detailed description regarding to
N50 reference is made to Miller et al. 2010. Assembly Algorithms for Next
Generation Sequencing data. Genomics. 95 (6): 315-327, which is incorporated
herein by reference).

