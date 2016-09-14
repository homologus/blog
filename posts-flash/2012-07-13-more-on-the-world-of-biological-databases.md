---
title: More on the World of Biological Databases
tags: []
categories:
- blog
---
Today is our day of frustration. It started with an [unsuccessful attempt to
get raw reads](http://www.homolog.us/blogs/2012/07/13/question-for-the-
readers-what-is-the-convention-for-submission-of-raw-reads-these-days/) for an
already published paper. We were debating about the difficulty of some
calculations on that huge RNAseq data set, but never expected retrieving the
libraries to be the biggest hurdle.
<!--more-->

Anyway, we decided to move on to a different analysis that also seemed very
easy at first. Let us explain what the plan was and where we stumbled, because
it is a good example of [the messy world of biological databases that we
discussed previously](http://www.homolog.us/blogs/2012/07/02/world-of-
biological-databases/).

Here was the planned analysis. We wanted to find out the genes neighboring a
set of microRNAs in the genome of mosquito _Aedes aegypti_. Very easy to do it
from annotation files, right?

Why _Aedes aegypti_? For no good reason other than its name starting with A.
Let us explain. For those unfamiliar with miRNAs,
[miRBase](http://www.mirbase.org/) is the central repository for miRNAs from
all organisms. The database has a very helpful [ftp
archive](http://www.mirbase.org/ftp.shtml), where it splits annotations for
various organisms. _Aedes aegypti_ happens to be the first one in that list.

We picked the
[aae.gff3](ftp://mirbase.org/pub/mirbase/CURRENT/genomes/aae.gff3) from
miRbase, and thought the rest of the tasks would be simple. The gff3 file gave
the coordinates for genome assembly AaegL1. So, we thought it would be a
matter of few more keystrokes to retrieve the remaining annotations for AaegL1
and find neighboring genes for all miRNAs.

Genomic data for _Aades aegypti_ is hosted by VectorBase - a database
maintained by Harvard, Ensembl and other very smart groups of people. The
latest annotation file I found there was for [A. aegypti annotation GFF,
Aaeg1.3 geneset](http://aaegypti.vectorbase.org/GetData/Downloads/?&archive_st
atus=all). It was not clear, whether the annotation was for genome assembly
AaegL1, but given that AaegL1 was the latest genome assembly, we presume the
annotation file was for the same assembly as the miRNA file in miRBase was.

That should be easy to check by comparing few coordinates from two gff files,
right? We failed.

The coordinates in miRBase file are given in terms of contigs.

The coordinates in Vectorbase file are given in terms of supercontigs.

We could not compare. Where is the contig-supercontig mapping file?

The miRNAs in miRBase were named as miR-124, mir-307, etc. It is the same
convention used in papers.

The miRNAs in VectorBase were named as AAEL012345, AAEL123455, etc. Who
invented those names, and how do they connect to miR-124, etc.?

At this point, we gave up and went for calculations from first principles. We
downloaded the miRNA sequences, downloaded the genome and mapped all genes.

