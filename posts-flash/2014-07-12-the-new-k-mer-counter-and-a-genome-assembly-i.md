---
title: The New K-mer Counter and a Genome Assembly - (i)
tags: []
categories:
- blog
---
Now that [Sebastian Deorowicz et al. published a damn good k-mer
counter](http://www.homolog.us/blogs/blog/2014/07/11/minimizer-revolution-
continues-with-kmc-2-k-mer-counter/), let us put it to some real work. The
first half of this two-part series will present some benchmarks on the
program, and the second half will discuss our use on a real-life genome
assembly problem.
<!--more-->

**Installation**

The installation of kmc 2 is fairly straightforward. We went to their website,
[downloaded the source code](http://sun.aei.polsl.pl/kmc.), compiled and
installed the program. The compilation needs Boost library, and if you have it
properly installed, everything else should go well to give you two programs -
**kmc** and **kmc_dump**. They also have pre-compiled binaries, but we
downloaded the source code to be able to poke around in the near future.

**Description of our project**

We have two sets of Illumina PE reads from a vertebrate species that swims.
The first set (set1) has 1,588,478,432 100nt reads and the second set (set2)
has 1,376,496,476 100nt reads. We did k-mer counting in set1, set2 and
set1+set2 for k=21, 27, 33, 39 and 45. We also did k-mer counting for set1 at
k=51, set2 at k=51 and set1+set2 at k=63. Yes, that is a lot of k-mer
counting.

This was done in a <del>32-core AMD server</del> (Corrected: 7/31/2014) Intel
Xeon server (four 8-core processors - CPU E7-8837 @ 2.67GHz) with 64-bit
Linux, non-SSD hard-drive and 512 GB RAM. The amount of RAM is somewhat
irrelevant for this highly efficient program.

**Time**

I started the k-mer counting tasks around midnight and got all results back by
~7AM. Wow! They were run serially, while the server was also running twenty
blastp jobs from another user.

set1 21mer counting took 585.523s.

set2 21mer counting took 567.74s.

set1+set2 21mer counting took 1507.44s.

set1 27mer counting took 612.069s.

set2 27mer counting took 534.832s.

set1+set2 27mer counting took 1361.61s.

set1 33mer counting took 1197.23s.

set1 33mer counting took 1037.95s.

set1 33mer counting took 2440.34s.

We noticed a jump in time needed for k>32, but no big differences after that
for k=33, 39, 45 and 51.

Here is the output file of first k-mer counting job (set1 for k=21) so that
you have an idea about all temporary space requirements.

>

1st stage: 258.373s

2nd stage: 327.15s

Total : 585.523s

Tmp size : 129830MB

Stats:

No. of k-mers below min. threshold : 3342104765

No. of k-mers above max. threshold : 0

No. of unique k-mers : 4734755445

No. of unique counted k-mers : 1392650680

Total no. of k-mers : 126120517209

Total no. of reads : 1588478432

Total no. of super-k-mers : 15387969776

1st stage: 252.294s

2nd stage: 315.446s

Total : 567.74s

Tmp size : 112898MB

**Command to Run and Output Files**

The command kmc can be run either on a single fasta/fastq file or multiple
files. The first two commands below are for single files and the third one is
for a file named 'list', which lists both fasta files.

>

./kmc -k21 -m200 -fa s200-data.fa out21-200 tmp

./kmc -k21 -m200 -fa s300-data.fa out21-300 tmp

./kmc -k21 -m200 -fa @list out21-both tmp

The program kmc produces two binary output files (out21-200.kmc_pre - 1.1G and
out21-200.kmc_suf 5.2G). Interestingly, in all k-mer counting examples we ran,
the size of the 'pre' file varied between 1073807452 bytes and 67174492 bytes,
and we do not have much clue why. This is where the code will come handy. One
clue - the file size appears to be k-dependent.

The program kmc_dump takes those two binary files, and gives you the k-mer
counts in two-column text format. Command to run -

> ./kmc_dump -cx0 out21-200 o

If the above commentary appears rather drab, the next commentary will surely
add some color to it.

