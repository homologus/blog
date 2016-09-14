---
title: Pacific Bio Sequences
tags: []
categories:
- blog
---
Many apologies to regular readers for not updating our blog. We got bogged
down with two major tasks -
<!--more-->

i) We got a new batch of Pacific Bio data and are trying to digest it,

ii) Our electrical engineering bug took control of our brain as we got into
studying FPGA/embedded systems for using in high-throughput bioinformatics.

In this post, we will add some information on Pacific Bio sequences that may
help other fellow passengers.

Pacific bio sequences fall at other extreme from Illumina Solexa data. The
reads are very long (~5kB), but they are also very noisy. Typically reads have
85% accuracy, which means every 100 nucleotides have 15 errors. Eeeks !!

We are just beginning, but let me walk through the experience so far step by
step. You will receive the following files from the sequencer (X is some
arbitrary file name) -

>

**Top_folder:**

X.mcd.hd5

X.metadata.xml

**Analysis_Results:**

X-02.log

X-03.log

X-04.log

X.bas.h5

X.ccs.fasta

X.ccs.fastq

X.fasta

X.fastq

X.sts.csv

X.sts.xml

What are the files?

The top folder contains raw data in hd5 format, which is PacBio's native data
format. The sequencer also performs introductory analysis to generate some
results, and those results are stored in Analysis_Results folder.

One important file in the Analysis_Results folder is x.ccs.fasta. This is the
one you need to first look into oo gain some confidence into the generated
data. Tt contains the cleanest assembled reads from the sequencing run. If you
have a reference genome, you need to first align the ccs reads on to your
reference genome. If that step fails, something went wrong with the sequencing
run.

In our case, the size of ccs file is only 1% of the raw fasta sequence files.
So, lot more sequences have not been included in ccs file, and to properly use
them, you need to use SMRT software from PacBio. You will also find
[PacBioToCA tools](http://sourceforge.net/apps/mediawiki/wgs-
assembler/index.php?title=PacBioToCA#Inputting_PacBio_RS_Sequences) useful.

Ideally one would like to run a de novo assembly with Pac Bio data, but that
is very hard because of high error rate of the raw sequences. So, researchers
are looking into two other possibilities -

i) Doing de novo assembly using Illumina or other short read technologies, and
using PacBio to do scaffolding/extending,

ii) Running an error-correction routine on Pac Bio data using Illumina
sequences, and then use those error-corrected reads for assembly. This is
where PacBioToCA can help. For example, you can use Velvet to generate contigs
from Pac Bio data, run error correction and then use error-corrected Pac Bio
to improve Velvet assembly.

You may find the following resources handy for making further progress-

i) [Michael Schatz's talk on SMRT assembly](http://schatzlab.cshl.edu/presenta
tions/2011-09-07.PacBio%20Users%20Meeting.pdf),

ii) [Pac Bio's webpage on how they assembled E. coli sequence from their
reads](http://www.smrtcommunity.com/Learn/How-To/E-coli-O104-Assembly),

iii) [A very helpful Seqanswers
thread](http://seqanswers.com/forums/archive/index.php/t-16895.html),

iv) [Pacbio's slides on SMRT technology](http://bio.pgp.jhu.edu/~jgreene/NextG
en/presentations/PacBio_SMRT_Sequencing_Sep_2011.pdf).

v) [A closer look at Pac Bio sequence
dataset](http://oelemento.wordpress.com/2011/01/03/a-closer-look-at-the-first-
pacbio-sequence-dataset/).

Enjoy !!

