---
title: Paircomp on Steroid (using Bowtie)
tags: []
categories:
- blog
---
Today's commentary will not only be helpful for those working on comparative
genomics, but will also allow us to navigate easily through the algorithm of
String Graph Assembler.
<!--more-->

With rapidly falling sequencing prices, genomes of many different related
species [have become accessible](http://www.nature.com/nature/journal/v450/n71
67/abs/nature06340.html), allowing biologists to find cis-regulatory regions
conserved over large evolutionary distances through sequence comparison. Two
months back, we presented the [paircomp
program](http://www.homolog.us/blogs/2011/12/08/paircomp-and-family-
relations/) from Eric Davidson's group and its associated analysis tools. At
that time, we were working on genome-wide comparison of two distant sea
urchins (_S. purpuratus_ and _L. variegatus_) and used the program
extensively.

We were a bit disappointed, when we found the paircomp program to be very slow
for comparing large genomic regions. In fact, it had a size cutoff of 300Kb
for each sequence, likely related to available RAM sizes in 2003-2005. We were
managing to stay within limits by running a pre-filter and only comparing
nucleotides around orthologous genes. Still, the speed of execution was a big
concern and we were looking for alternatives. The program was written nearly a
decade back, and the world of bioinformatics moved a lot ahead since then. In
fact, Dr. Shoudan Liang, an ex-colleague, designed a faster algorithm in 2005.
We were ready to test his algorithm to speed up our pipeline, but a faster
option seemed promising.

Before we discuss the faster algorithm, here is a brief outline on how the
paircomp program works. It picks up all short nucleotide segments (k-mers) of
some size from one of the two sequences and finds their matches in the other
sequence. A certain degree of mismatches are allowed. If you are familiar with
NGS programs, you instantly realize that one of the sequences can be broken
into short reads and compared with the other sequence using short read mapping
programs. You also know that the most memory-efficient way to do the above
task is to use a Burrows-Wheeler transform-based algorithm. That is
essentially what 'paircomp-on-steroid' does.

Here are some results. We compared a 145Kb sequence from S. purpuratus
(Scaffold2782, assembly version 3.1) with a 65Kb sequence from L. variegatus
(Scaffold4548, assembly version 0.4).

We ran the command 'paircomp Sp-Scaffold2782 Lv-Scaffold4548 20 .9 out' to
find all matching 20mers between two segments. Up to two mismatches were
allowed (20*.9=18). The program took 6 minutes to run (Time stamps -Sat Feb 18
14:30:46 PST 2012 to Sat Feb 18 14:36:37 PST 2012).

'Paircomp-on-steroid' constituted of four programs.

i) A perl script working as preprocesser, and splitting the Sp scaffold into
20-mers into a FASTA file.

ii) Bowtie-build to create an index from Lv-Scaffold4548.

iii) Bowtie to compare the FASTA k-mer file from Sp to compare with Bowtie
index from Lv.

iv) A perl script to convert the Bowtie output into the same form as the
paircomp output.

`

bowtie-build Lv-Scaffold4548 lv

./pre-process.perl Sp-Scaffold2782 > sets

bowtie -f -a lv sets out-x

./post-process.perl out-x > out

`

They took only 4 seconds to run on the same sequence pairs (Time stamps - Sat
Feb 18 14:45:51 PST 2012 to Sat Feb 18 14:45:55 PST 2012).

The first program (paircomp) reported 39376 matching regions and the second
program (paircomp-on-steroid) reported 39338 matching regions. All of them
were present in the paircomp output. The 38 extra matches from paircomp are
all from sequences with one or more Ns, and Bowtie ignored N sequences. Apart
from those, the results were identical.

For reference, here is the code for the pre-processor.

`

#!/usr/bin/perl

$N=20;

open(IN,$ARGV[0]);

while()

{

if($_=~/>(\S+)(.*)/) {$name="$1"; $name=~s/.*Mm//; } else {
$assoc{$name}.=uc($1) if ($_=~/^(.*)\s*$/); }

}

close(IN);

foreach $key (keys(%assoc))

{

$seq=$assoc{$key}; $len=length($seq);

for($i=1; $i<$len-$N+2; $i++)

{

$short=substr($seq,$i-1,$N);

$x=$i-1;

print ">$x\n$short\n";

}

}

`

Here is the post-processor that converts Bowtie output to paircomp format -

`

#!/usr/bin/perl

open(IN,$ARGV[0]);

while()

{

@s=split(/\s+/,$_);

$t=$s[7]; $t=~s/://g;

$N=20-(length($s[7])-length($t));

$count=0;

$str=1; $str=-1 if($s[1] eq "-");

$loc=$s[3]; $loc+=19 if($str eq "-1");

print "$s[0]\t$loc\t$N\t$str\n";

}

`

