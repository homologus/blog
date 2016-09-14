---
title: Is BWA-MEM as Good as BLASR for Aligning PacBio Reads? - Part 1
tags: []
categories:
- blog
---
We downloaded [raw reads and alignment
file](http://datasets.pacb.com/2013/Human10x/READS/index.html) of human genome
data [released by Pacbio
yesterday](http://www.homolog.us/blogs/blog/2013/10/22/pacbio-releases-
library-covering-human-genome-10x/). It came from a postdoc research project
by [Mark Chaisson](http://eichlerlab.gs.washington.edu/mchaisso.html) at the
Eichler lab in University of Washington. Please note that his picture below is
taken on one of those two rare days during Seattle summer, when the sun comes
out :)
<!--more-->

![](http://eichlerlab.gs.washington.edu/images/mchaisso.jpg)

With his long experience as Pavel Pevzner's student, author of BLASR alignment
program as a PacBio employee and at the Eichler lab, Mark can provide far
better perspective of the data than what we can do here. So, please excuse our
lame attempt in using it to answer a few basic questions.

One question that often pops up in our mind is whether BWA-MEM is as good as
BLASR for aligning PacBio reads on to a genome. [BWA-
MEM](http://arxiv.org/abs/1303.3997) is the long read alignment program
written by Heng Li. We covered it extensively in our earlier commentaries.

[Mapping God Found Scientifically Dishonest by Anonymous Peer
Reviewers](http://www.homolog.us/blogs/students/2013/05/29/mapping-god-
scientifically-dishonest/)

[A Number of Informative Comments from Heng Li on BWA-MEM
Aligner](http://www.homolog.us/blogs/blog/2013/06/20/a-number-of-good-
comments-on-bwa-mem/)

[Digging into BWA-mem Code](http://www.homolog.us/blogs/blog/2013/06/29/bwa-
code/)

We also found "[An open peer review of bwa mem](http://darlinglab.org/open-
peer-review-bwa-mem)" by The Darling lab that is quite informative, and
[here](https://github.com/lh3/mem-paper/blob/master/response_to_aaron.md) is
the informal response from Heng Li.

Over the last few days, we have been [dismantling the
code](http://homolog.us/wiki1/index.php?title=BWA) of BWA mem just like we did
earlier for SOAPdenovo2, Minia and DSK (k-mer counting code from Rayan
Chikhi). Today we will update the wiki page more to explain the files and
functions within BWA. Overall, the mapping strategies of BWA-MEM and BLASR
appear very similar. Both methods first find a number of short seeds (i.e.
perfect match) between the query and the reference using BWT. Then they both
use Smith Waterman to fill up the regions between the seeds. Therefore, it is
natural to ask, whether their performances match for PacBio reads. The
difference between the algorithms is that the seeds of BLASR are of constant
size, whereas BWA-MEM tries to find seeds of maximal size. However, when you
consider the fact that multiple constant sized seeds of BLASR can be combined
into a super-seed, above differences should not affect the mapping quality.
BWA-MEM uses combined forward-reverse index of the genome, which likely speeds
up the seeding step.

Our question has three parts:

(i) How different are the programs in aligning long PacBio reads on to a
reference genome?

(ii) Can the parameters of the BWA-MEM algorithm be changed from default to
improve performance?

(iii) Can the code of the BWA-MEM be tweaked to improve performance?

In part 2 of this commentary, we will address those questions up to our
highest level of incompetence.

