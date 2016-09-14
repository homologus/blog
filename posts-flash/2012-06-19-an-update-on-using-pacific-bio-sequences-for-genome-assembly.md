---
title: An Update on Using Pacific Bio Sequences for Genome Assembly
tags: []
categories:
- blog
---
We are really amateurs, when it comes to Pacific Bio sequences. How amateur
are we? A few weeks back, we [commented on our first PacBio
library](http://www.homolog.us/blogs/2012/05/02/pacific-bio-sequences/) and it
appears on the first page of google search with keywords ['Pacific bio
sequences'](https://www.google.com/#hl=en&sclient=psy-
ab&q=pacific+bio+sequences+analysis&oq=pacific+bio+sequences+analysis). So we
guess we are no less informed than the rest of the world :)
<!--more-->

Nevertheless, here we like to report that our efforts of using PacBio
sequences in a genome assembly has been successful. PacBio reads were used
solely for scaffolding short contigs previously assembled from Illumina reads.
Pacific Bio reads are long (2Kb average in our case) but very noisy, whereas
Illumina reads are short and clean. Therefore, one can develop a strategy of
using the best of each technology into a combined effort.

Here are few small comments on what worked and what did not to help you avoid
few learning steps.

a) Alignment tools like BLAST are of less use for PacBio data, because the
reads are very noisy. Therefore, the company makes another alignment program
named BLASR available. After going through registration and few other steps,
we downloaded BLASR, but we were unable to install it due to a missing
library. Being impatient as we were, we decided to simply map all K-mers
(derived from Illumina) on the PacBio reads using Bowtie and proceed with
further analysis. That seemed to have worked and we did not bother with BLASR.

b) The second thing you need to remember in using PacBio reads is that they
are circular, and you cannot use them as plain Sanger reads while connecting
contigs.

A picture will make this point clear. Here we show a genomic region and a
possible PacBio read from the same genomic region -

![](http://www.homolog.us/blogs/wp-content/uploads/2012/06/pacbio-300x101.png)

We are now doing a type of analysis with the PacBio library, where we plan to
correct PacBio reads using Illumina to build clean reads. This step is used
primarily to build the repetitive regions of the genome. The results will be
reported in a follow up commentary.

Note.

Reader Markus kindly suggested PacBioToCA software tools developed to do the
above task. It is available from
[Sourceforge](http://sourceforge.net/apps/mediawiki/wgs-
assembler/index.php?title=PacBioToCA).

> Hybrid error correction and de novo assembly of single-molecule sequencing
reads

Sergey Koren, Michael Schatz, Brian Walenz, Jeffrey Martin, Jason Howard,
Ganeshkumar Ganapathy, Zhong Wang, David A. Rasko, W. Richard McCombie, Erich
D. Jarvis, and Adam M. Phillippy

About PacBio RS

The PacBio RS sequencing instrument from Pacific Biosciences is a single-
molecule sequencer that is able to generate long-reads (mean: 2,246, max:
23,000). Unfortunately, these sequences have a low accuracy, averaging only
84.6%. While It is possible to read each circularized molecule multiple times
to get higher accuracy sequences, this produces significantly shorter
sequences (mean: 423, max: 1,915).

About pacBioToCA

The pacBioToCA script is a correction pipeline to enable the use of the long-
read sequences produced by the PacBio RS instrument. To algorithmically deal
with the error, we require alternate high-identity sequences (454, Illumina,
or PacBio circularized sequences) to re-call accurate consensus. Celera
Assembler includes a pipeline, pacBioToCA, to generate FRG File (as well as
fasta and qual) from PacBio RS sequences given short-read high-identity data
to correct with.

