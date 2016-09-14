---
title: An Experience with New Trinity
tags: []
categories:
- rnaseq
---
We have been trying to assemble a large transcriptome library of size ~200GB
(Illumina fastq file size for full PE library, not nucleotide count) using
Trinity. The server being used has 32 cores and 512G RAM. We were able to
assemble similar-sized transcriptome libraries from other organisms in the
same server, and the amount of RAM does not seem to be a problem here. Still,
we are never able to complete the assembly for some reason.
<!--more-->

The first step in Trinity is k-mer counting. Earliest releases came with
Trinity's own k-mer counting implementation. Then they upgraded to Meryl and
Jellyfish, and Jellyfish appears to be the only option at present.

At first, we tried full Trinity on the entire library. K-mer counting step
completed quickly within a few hours. Then we got into Inchworm, which took a
day or two to finish. The latest Trinity runs a Bowtie step between Inchworm
and Chrysalis, and the Bowtie step also completed in reasonable time.
'Reasonable' in our count is measured in days, not hours (why is explained
below).

Then Trinity got stuck into 'GraphFromIwormFasta.out' for ever. That is the
first step in Chrysalis. Let me tell you how long our program is stuck in that
step. When the Chrysalis folder was created, my son was in diapers. Now he is
about to finish high-school and Trinity had not added a single byte into the
'GraphFromIwormFasta.out' file.

Jokes aside, we did not have the patience to see our program being stuck at
that step after a week. We abandoned the full run and went to digital
normalization.

On the full library, digital normalization took one day to **not complete**.
After 24 full hours, we gave up on digital normalization and went for [our own
cocktail](http://www.homolog.us/blogs/2012/02/28/a-strategy-for-running-
trinity-on-very-large-ngs-library-or-reducing-number-of-genes/). This method
essentially removes most singleton reads and assembles the high frequency
reads. Then the singletons are taken care of in a later step. Conceptually, we
are doing k-mer filtering with k=100, because the read size is 100nt in our
case. Usually, genes come fragmented or short as a result, but at times, that
is better than no assembly ever.

Our method did not disappoint and we got preliminary assembly within a day.
The reads that did not assemble on any transcript are passed through another
digital normalization + Trinity step. The size of library being passed to
Trinity is 10G. Digital normalization finished within a day, but Trinity is
still running, and guess what, it is stuck at the infamous
'GraphFromIwormFasta.out' step for the last 10 hours.

To fix short genes, we run them through another cocktail. We map all reads on
to them and then pass those little blocks through Trinity. As it appears, new
Trinity is terribly slow for very small read libraries likely because of the
bowtie-build step. So, we split the job into a remote Condor cluster, but
Trinity did not run. That was puzzling, because we did this step many times
with early versions of Trinity. What is the problem? Previously, we passed the
compiled Trinity folder and reads to the remote server, and got back the
results. This time it needed bowtie, bowtie-build, and bowtie, bowtie-build
again. We tried to place bowtie in right places, fix the paths, but finally
figure it was easier to download the original plain vanilla Trinity from
sourceforge and run. That worked well and we had results in an hour.

However, we are still worried about the remaining library that is stuck at
'GraphFromIwormFasta.out'. I promised my son that the assembly will be
complete before he completes high school, and time is running out. Can anyone
explain what is going on?

