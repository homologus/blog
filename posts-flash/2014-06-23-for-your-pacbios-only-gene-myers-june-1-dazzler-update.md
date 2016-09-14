---
title: "'For Your Pacbios Only' - Gene Myers' June 1 Dazzler Update"
tags: []
categories:
- blog
---
It is exciting to find both Pevzner and Myers group continue to post new ideas
on genome assembly as they started doing twenty years back. Gene Myers posted
a new update earlier this month on Dazzler DB. All codes are available from
github at [this link](https://github.com/thegenemyers/DAZZ_DB).
<!--more-->

[The Dazzler DB: Organizing an Assembly
Pipeline](http://dazzlerblog.wordpress.com/2014/06/01/the-dazzler-db/)

>

Assembling DNA sequence data is not a simple problem. Conceptually it
generally can be thought of as proceeding in a number of sequential steps,
performed by what we call phases arranged in a pipeline, that perform certain
aspects of the overall process. For example in the OLC assembly paradigm, the
first step is to find all the overlaps between reads (O), the second step is
to then use the overlaps to construct a layout of the reads (L), and the final
phase is to compute a consensus sequence over the arrangement of reads (C).
One can easily imagine additional phases, such as a scrubber that detects
chimeric reads, a cleaner that corrects read sequence, and so on. Indeed, the
header banner for this blog shows a 7 stage pipeline that roughly realizes our
current dazzler prototype. To facilitate the multiple and evolving phases of
the dazzler assembler, we have chosen to organize all the read data into what
is effectively a database of the reads and their meta-information. The design
goals for this data base are as follows:

  1. The database stores the source Pacbio read information in such a way that it can recreate the original input data, thus permitting a user to remove the (effectively redundant) source files. This avoids duplicating the same data, once in the source file and once in the database.

* The data base can be built up incrementally, that is new sequence data can be added to the data base over time.

* The data base flexibly allows one to store any meta-data desired for reads. This is accomplished with the concept of tracks that implementers can add as they need them.

* The data is held in a compressed form equivalent to the .dexta and .dexqv files of the data extraction module. Both the .fasta and .quiva information for each read is held in the data base and can be recreated from it. The .quiva information can be added separately and later on if desired.

* To facilitate job parallel, cluster operation of the phases of our assembler, the data base has a concept of a current partitioning in which all the reads that are over a given length and optionally unique to a well, are divided up into blocks containing roughly a given number of bases, except possibly the last block which may have a short count. Often programs can be run on blocks or pairs of blocks and each such job is reasonably well balanced as the blocks are all the same size. One must be careful about changing the partition during an assembly as doing so can void the structural validity of any interim block-based results.

