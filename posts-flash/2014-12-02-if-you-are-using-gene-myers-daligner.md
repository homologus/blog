---
title: If You are Using Gene Myers' Daligner
tags: []
categories:
- blog
---
After a few false starts, we managed to make Daligner work optimally on a
large Pacbio library. Here is a quick summary of our experiences to help
anyone following the same path.
<!--more-->

\---------------------------------

**Algorithm**

The algorithm is described in the following blog post and is summarized below.

[In DALIGN Paper, Gene Myers Delivers a Major Blow to His Biggest
Competitor](http://www.homolog.us/blogs/blog/2014/07/28/in-dalign-paper-gene-
myers-delivers-a-major-blow-to-his-biggest-competitor/)

Like most other alignment programs (BWAMEM, BLASR), it has two components. The
first part searches for common kmers present in reference and target sequence.
The other competing programs use Burrows Wheeler transform of reference, but
Gene Myers developed a very clever algorithm to take advantage of L1 caches
and perform a direct comparison.

The second part does finer alignment between the reference and target, and
most competing programs use Smith-Waterman to do local alignment. Instead,
Gene Myers used O(ND) algorithm, which usually faces difficulty in aligning
long regions due to rapid rise of off-target alignments. Once again, Gene
Myers used a Pacbio-specific condition (complete randomness of errors) to cut
down those unlikely alignments.

\---------------------------------

**Execution**

[The programs](https://github.com/thegenemyers) are well documented, but if
things do not work for the first time, do try out the simulator that comes
with DAZZLER_DB. Run the following commands and you are guaranteed to see
results. Then you can compare with your case to debug the step that is not
working.

`

> simulator 1.0 >G.fasta // Generate a 20x data sets of a 1Mb genome

> fasta2DB G G.fasta // Create a compressed data base of the reads, G.db

> rm G.fasta // Redundant, recreate any time with "DB2fasta G"

> DBsplit -s11 G // Split G into 2 parts of size ~ 11MB each

> DBdust G.1 // Produce a "dust" track on each part (just to illustrate)

> DBdust G.2

> Catrack G // Create one track for the entire DB from the 2 sub-tracks

> rm G.*.dust.* // Clean up the sub-tracks

> DBstats G // Take a look at the statistics for the database

`

Here are the common pitfalls -

(i) The FASTA file headers need to be in Pacbio format that includes quality
score. You can do that by writing a simple script that converts each non-
Pacbio fasta ID to something like this.

`>Prolog/$ID/0_$L RQ=0.850`

(ii) Do remember to run daligner with the '-d' option (dust cleanup of low-
complexity kmers), because the program may crash (Seg fault) otherwise on
large blocks of reads. (Note. We were working with the July 22 release of the
code, where the problem was quite frequent. Not sure about the latest one, but
saw [someone to report a
bug](https://github.com/thegenemyers/DALIGNER/issues/1) on exactly the same
point. We are now using the latest code, but did not bother to check without
'-d' to see whether the problem is gone.)

(iii) If you want to run daligner with different number of threads than
default (=4), some code hacking is necessary. Go to 'filter.h' and change the
following two lines correctly. Recompile and everything should work as
expected.

`#define NTHREADS 32 // Must be a power of 2

#define NSHIFT 5 // log_2 NTHREADS`

(iv) For faster execution, you may want to run the code with '-t' option to
reduce the number of commonly present kmers.

(v) Jared Simpson wrote a new module for processing daligner output that you
may find handy. We have not used it yet.

[Quick Update on Pacbio and DALIGNER Jared Simpsons GFA
Module](http://www.homolog.us/blogs/blog/2014/11/03/quick-update-on-pacbio-
and-daligner/)

If anything else comes up, we will add to the above list.

