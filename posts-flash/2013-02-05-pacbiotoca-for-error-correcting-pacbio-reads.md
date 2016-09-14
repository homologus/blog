---
title: PacBioToCA for Error-correcting Pacbio Reads
tags: []
categories:
- blog
---
We have about 1.2 Gb of PacBio sequences for a fish genome along with plenty
of Illumina data. So far, we processed the PacBio reads using BLASR and our
home-cooked kmer-based algorithms, but yesterday we decided [to give
PacBioToCA a try](http://www.homolog.us/blogs/2012/06/19/an-update-on-using-
pacific-bio-sequences-for-genome-assembly/) after reading encouraging e-mail
comments from [Lex Nederbragt](http://flxlexblog.wordpress.com/). While the
program is still running, here are bits and pieces of information for others
interested in running it.
<!--more-->

\---------------

**What does PacBioToCA stand for?**

Pacbio-->to-->CA

CA stands for Celera Assembler. The code is expected to convert PacBio reads
to reads in CA format ('frg'), but it also produces fasta and fastq versions
of error-corrected reads. For most of our data, frg file is essentially a
wrapper on fasta and fastq libraries.

\---------------

**How to run?**

The [sourceforge webpage on PacBioToCA](http://sourceforge.net/apps/mediawiki
/wgs-assembler/index.php?title=PacBioToCA) is good enough to let you get
started. If you do not have Celera assembler, you will need to install it
first. You can either copy the binary files from Sourceforge, or download
source code and compile Celera assembler yourself.

After installing Celera assembler, please follow these steps to clean PacBio
reads:

i) PacBioToCA cleans PacBio reads based on a clean set of reads (Illumina,
454). So, you will need to create a folder and copy PacBio reads and clean
reads there.

ii) If your PacBio reads are in fasta format, you will need to create fastq by
using [convertFastaAndQualToFastq utility](http://www.cbcb.umd.edu/software/PB
cR/data/convertFastaAndQualToFastq.tar.gz). It is a simple program and adds
two extra lines after every fasta sequence entry. All quality scores are
marked as 'I'.

iii) You will need to create a frg wrapper file for your clean reads. The
script [FastqtoCA](http://sourceforge.net/apps/mediawiki/wgs-
assembler/index.php?title=FastqToCA) allows you to create the frg wrapper
file.

iv) You will need to create a pacbio.spec file. To start with, you can [copy
this file](http://www.cbcb.umd.edu/software/PBcR/data/sampleData/pacbio.spec)
and get started. It is prepared for high-memory multi-core machines. If you
are running on a grid, use a [different
file](http://www.cbcb.umd.edu/software/PBcR/data/sampleData/pacbio.SGE.spec).

Once all files are ready, please run -

`pacBioToCA -l test -t 32 -s pacbio.spec -fastq pacbio.fastq clean.frg

`

-l test = is the name, where you want your output 

-t 32 = number of threads 

-s pacbio.spec = spec file listed in (iv) above 

-fastq pacbio.fastq = the PacBio file you want to get cleaned 

clean.frg = frg wrapper for clean Illumina or 454

The above command will allow you to get started and you will receive your
clean PacBio data in about 300 days !! (no kidding)

\---------------

**Where can things go wrong?**

We found a [highly informative SeqAnswers
thread](http://seqanswers.com/forums/showthread.php?t=18478) with comments
from many bioinformaticians, who tried PacBioToCA script. There were many
complaints regarding speed of the program.

>

I'm also running into speed issues. My 50x coverage was estimated to take
4weeks to complete.

I would be surprised if all the people using it are ready to wait that long
:-)

Above one is not the worst. Another user complained -

> I also tried to run the pacbioToCa pipeline, but for our case it initially
took 200days to complete. It turned out that we have a huge E.coli
contamination, making the coverage of that genome over 5000x.

We are puzzled that someone waited for 200 days before stopping the script and
trying to figure out what went wrong !!

There were other hopeful comments such as from one user, who reduced the
running time from 8 days to 1 hour (!!!) by modifying spec file slightly. A
modified spec file is posted in the above thread.

\---------------

**How does PacBioToCA work?**

Above comments prompted us to take a look at the code for PacBioToCA to make
sense of what is going on. We do not fully understand it yet, but here is a
rough sketch.

1\. PacBioToCA is a 514 line PERL wrapper script, which calls another large
PERL script called runCA to do first part of the analysis. What is runCA? It
stands for 'run Celera Assembler'.

2\. The script runCA calls **Meryl** executable for counting k-mers in good
reads.

Few links on runCA -

[runCA Dissection](http://sourceforge.net/apps/mediawiki/wgs-
assembler/index.php?title=RunCA_Dissection)

[runCA pdf guide](http://wgs-assembler.sourceforge.net/runCA51.pdf)

3\. Then runCA creates a script 'mertrim.sh' that calls 'merTrim' executable
to trim good reads based on k-mer frequency. The executable merTrim compiles
from /wgs-7.0/src/AS_MER directory of Celera assembler.

4\. Script runCA creates a script called 'overlap.sh' that calls
**overlapInCore** next to determine overlaps. This executable compiles from
C-code in 'wgs-7.0/src/AS_OVM' directory of Celera Assembler).

`/home/PacBioToCA/Linux-amd64/bin/overlapInCore -G --hashbits 24 --hashload
0.75 -t 2 -h 13000006-13200005 -r 1-50000000 --hashstrings 200000
--hashdatalen 20000000 -k 14 -k
/home/PacBioToCA/working/pacbiotoca/temptry/0-mercounts/asm.nmers.obt.fasta -o
/home/PacBioToCA/working/pacbiotoca/temptry/0-overlaptrim-
overlap/001/000066.ovb.WORKING.gz -H 1-1 -R 1-1
/home/PacBioToCA/working/pacbiotoca/temptry/asm.gkpStore`

Cleaned up:

`overlapInCore -G --hashbits 24 --hashload 0.75 -t 2 -h 13000006-13200005 -r
1-50000000 --hashstrings 200000 --hashdatalen 20000000 -k 14 -k
temptry/0-mercounts/asm.nmers.obt.fasta -o temptry/0-overlaptrim-
overlap/001/000066.ovb.WORKING.gz -H 1-1 -R 1-1 temptry/asm.gkpStore`

For our data, 'overlap.sh' will be run 19798 times and only 66 of them
complete so far in a day. So, we are looking at 299 days of wait time.

Edit. On second look, things are not that bad. Much of the time was spent on
running Meryl for k-mer counting. The script overlap.sh started to run only
today, and completed 116 in 4 hours. So, we are looking at 29 days, not 299
days.

5\. Finally PacBioToCA calls correctPacBio, another executable that compiles
from wgs-7.0/src/AS_PBR/CorrectPacBio.cc.

Adventurous users may separately run above components of PacBioToCA on small
test data, and then write their own pipeline optimized for their computing
hardware (# of cores, RAM, etc.). If we are successful, we will let you know.

