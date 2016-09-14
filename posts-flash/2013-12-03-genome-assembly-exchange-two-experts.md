---
title: Genome Assembly - An Exchange between Two Experts
tags: []
categories:
- blog
---
Both Rayan Chikhi (an author of Minia assembler) and Anton Korobeynikov (an
author of SPAdes assembler) commented in [our earlier post on a recent PLOS
One paper](http://www.homolog.us/blogs/blog/2013/11/25/plos-one-paper-
comparing-memory-efficient-genome-assemblers-stand-alone-cloud-
infrastructures/) that benchmarked a number of low-memory genome assembly
programs. The comments are quite informative for those not familiar with the
intricate details of such programs, and therefore we decided to present them
in a new commentary.
<!--more-->

Anton said:

> The results are definitely misleading. People should stop comparing to
Velvet as single gold reference assembler. GAGE-B clearly shown that state-of-
the-art assemblers can easily beat Velvet by 20x in terms of N50. E.g. for R.
sphaeroides dataset from GAGE-B Velvet achieved N50 of 24kb (3 kbp in the
paper with plenty of misassemblies), MaSuRCA achieved 130 kbp and both Ray and
SPAdes were able to produce contigs of N50 with more than 500 kbp (Ray was not
included into GAGE-B, this is our internal run with parameter tuning like in
GAGE-B).

So really, the results of the paper need to be redone using both recent data
and recent assemblers.

....

There is the usual time / memory / quality tradeoff. However, for me, the
paper looks like the indirect way propagating two their own approaches (DiMA,
ZeMA, etc.), rather than compare the assemblers properly.

For example, the authors claim that Our experiments prove that it is possible
to generate draft assemblies of reasonable quality on conventional multi-
purpose computers with very limited available memory by choosing suitable
assembly methods

This is not true. The quality of of the results (look for N50 and
misassemblies in Tables 3-5) is below the level of acceptance these days. They
effectively reported the results 10 times lower than in GAGE study and ignored
all the results from GAGE in order to deduce the conclusions. Note also the
differences in the methodologies GAGE tried to derive best assemblers
selecting the best parameters. The authors simply fixed k-mer length to 31 and
thats it.

Combing the authors provided tables and GAGE tables, we can instead easily say
Our experiments prove that it is NOT possible to generate draft assemblies of
reasonable quality on conventional multi-purpose computers with very limited
available memory by choosing suitable assembly methods. In order to achieve
the reasonable quality the proper assembly methods requiring more memory are
necessary.

So, the conclusions of the paper would be the opposite! However, judging from
how they worked with GAGE results and methodologies, I wont trust the authors
anymore, instead I demand all the work to be thoroughly redone, and the true
data to be put in the tables.

Perhaps, we can ask Rayan to run Minia on GAGE / GAGE-B data and report the
results? :) This way we at least will be sure that Minia results are of GAGE-
level quality.

Rayan replied -

> All right Anton, good idea! Heres my informal Minia assembly of the GAGE
chromosome 14 dataset.

Minia version: 1.5938

Reads taken: all the raw reads, i.e. fragments and short jump and long jump.

Parameters k=53 and min_abundance=5 were given by Kmergenie (command line:
./kmergenie list_reads).

Command line: minia list_reads 53 5 100000000 chr14_k53_m5

Peak mem: 147 MB

Time: 73 mins

Excerpt from Quast output:

# contigs (>= 0 bp) 82433

Total length (>= 0 bp) 87199867

Largest contig 27533

N50 3054

NG50 1965

NA50 3043

NGA50 1954

# misassemblies 18

# local misassemblies 17

All those metrics look much better than in Table 5..

Here is what differs from their assembly: 1) parameters are optimized 2) that
new Minia version yields better genome coverage than older ones. 3) I used all
the GAGE reads, they used only the fragments.

A few more notes on the paper in general:

1) Many of the low-memory assemblers tested in the PLOS One paper do not
include a scaffolder nor a gap-filler. Those tested in GAGE and GAGE-B at
least have a scaffolder. Thus it is not surprising that the GAGE/GAGE-B
contiguity stats look much better.

2) GAGE used the best possible error-corrected read dataset for each organism.
The Plos One paper apparently used the raw data, which in my experience gives
worse assemblies.

3) GAGE also picked reasonable k-mer sizes for each dataset separately.

In summary, the benchmarks in this paper are fair, in the sense that they ran
all the programs in similar conditions. But its too bad that those conditions
led to assemblies that were either very poor (e.g. for chr14), or that looked
poor in comparison to GAGE, because of the lack of tuning.

By the way, Anton, not sure if the following statement is an accurate
comparison:

E.g. for R. sphaeroides dataset from GAGE-B Velvet achieved N50 of 24kb (3 kbp
in the paper with plenty of misassemblies), MaSuRCA achieved 130 kbp and both
Ray and SPAdes were able to produce contigs of N50 with more than 500 kbp

That 24 kbp N50 figure for Velvet/GAGE-B is for the MiSeq data, it drops to 13
kbp with the HiSeq data. But, is the R. sphaeroides Hiseq dataset from GAGE-B
the same as from GAGE? In my experience, the raw GAGE dataset is quite
challenging to assemble. Also for the MiSeq dataset, Spades N50 is at 118 kbp
in the GAGE-B paper. A newer version can do 500 kbp? :)

When reading such exchanges, readers should not assume that one person is
right and therefore the other has to be wrong. A genome assembly problem is
multi-faceted and both of them can be right in covering different aspects.
Given that the exchange is based on GAGE vs PLOS One comparison, the same can
be said about various benchmarking papers. There are so many variables in
comparing two assemblers that asking which assembler is the best is too
simplistic, unless one qualifies it with machine type, RAM size, library type
and a number of other parameters. On the other hand, it is often impossible to
test for all those parameters and still come up with a useful metric.
Especially the 'machine type' variable is the hardest to quantify, because it
includes disk speed and RAM size, which can change the speed of execution
quite a bit. Throw in different read sizes and different types of libraries
(PacBio?) and you are in a complete mess.

The exchange should rather be taken as the types of things a bioinformatician
should keep in mind in working on his problem. Often conventional wisdom
fails, as we describe below.

**a) Hardware Limitations:**

A few days back, we were trying to benchmark DSK, a k-mer counting program
written by Rayan. We ran it with default options and the program finished in 3
hours. The machine happened to have 32 cores and fairly big RAM. So, we
thought of running it with multi-threading option with lot of RAM to finish
the run in fraction of that time. Lo and behold, the program continued to run
for 8 hours with no result. What was going on?

With more resources, the processor cores, RAM and disk started to compete with
each other to move data from here to there, and spent less time on actual
computation (which is minimal for k-mer counting). So, essentially we had
Craig Barrett's breakfast problem [described
earlier](http://www.homolog.us/blogs/blog/2013/05/05/the-future-of-computers-
multicore-and-the-memory-wall/). Too many cooks were opening and closing the
fridge, and very few actually got time to fry omelettes.

**b)RAM:**

We write RAM separately, because in many servers it is the biggest limiting
factor. Amazon charges you an arm and a leg, if you want to rent a computer
with high RAM. What can you do? You can design your data structure more
efficiently, but beyond that the only solutions are - (i) crashing, (ii)
shifting data between RAM and hard-drive during assembly. The speed of the
second solution can be increased quite a bit by replacing the hard disk with
SSD, and SSD storage does not cost that much these days. After all, you can
design a server with one smaller SSD storage for computation and another
slower disk for permanent storage. That is small increase in cost with huge
added benefit.

**c) Multi-threading:**

Many bioinformatics programs are written to use multiple cores, but their
scale up is not always linear as we explained earlier. How do you figure out
what is going on? You may have to think about what the program is doing and
break it down into smaller problems to identify the bottleneck.

**d) Cache Size - Problem with Small Pieces: **

A few days back, we were trying to benchmark BWA-MEM. To understand the
performance of its various steps, we decided to replace the human genome with
a tiny genome. At that point, everything started to behave abnormally and we
got results much faster than we expected. What happened?

In our usual model of computing, a processor gets its data from the RAM.
However, when the genome is too small, the processor fitted the entire memory
block into its cache memory (memory within the chip) and did not need to
access RAM any more. Very few bioinformatics programs use this aspect of
processing, even though considerable speed gain can be achieved from using the
cache effectively.

Those are just four aspects in producing machine-to-machine difference in
performance of bioinformatics programs and we have not gone into algorithmic
difference, library differences or contig assembly vs scafold assembly.

