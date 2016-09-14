---
title: Happy New Year
tags: []
categories:
- blog
---
I know it is February 9th, over one month past when we traditionally send New
Year's cards in USA. However, we have a global readership and someone in some
corner of the world must be celebrating arrival of new year today. :) We were
in Singapore last week watching the city adorned with giant dragons on
occasion of [Chinese New Year](http://www.chinapage.com/newyear.html).
Thailand and many parts of India will begin their new year [in about two
months](http://en.wikipedia.org/wiki/Pohela_Boishakh). No matter where you
are, we wish you happiness and success in the days and months ahead.
<!--more-->

We apologize for the brief hiatus of two months from reporting on
bioinformatics. Those of you, who emailed us, expect to receive replies
shortly. This absence was not due to nothing newsworthy happening in the world
of transcriptomics, but we ourselves got very busy developing and testing a
new algorithm for genome assembly. Its main purpose was to reduce the amount
of memory required to assemble a large genome, and to develop an approach that
could be implemented in a cluster in parallel fashion (without inter-process
communication as in ABySS). Our new algorithm worked as a proof of concept,
but it would need some work before an out-of-the-box software program can be
presented to the community. Nevertheless, working on it helped us understand
many of the intricacies of short read data sets and assemblies, whereas most
users of readily available programs are limited to tweaking parameters
blindly. We will follow up on this topic in the coming days.

In the meanwhile, several promising discoveries were reported by various
groups to excite our readers. We shall list them here and delve into their
details in later posts.

1\. **Transcriptome assembler from BGI**

We have not covered the details of [SOAPdenovo assembler from
BGI](http://soap.genomics.org.cn/soapdenovo.html), but it is [one of the
strongest genome
assemblers](http://genome.cshlp.org/content/genome/21/12/2224.full.html) for
next-generation sequences. This assembler uses de Bruijn graph approach just
like Velvet, ABySS, Trinity and other available programs. BGI recently
reported a transcriptome module 'SOAPdenovo-Trans' that can be useful for
transcriptome assembly. We have not tested it ourselves, but users of
SOAPdenovo may find the module handy.

2\. **Genome assembler SGA that uses Burrows-Wheeler transform**

An interesting paper titled ['Efficient de novo assembly of large genomes
using compressed data
structures'](http://genome.cshlp.org/content/early/2012/01/22/gr.126953.111)
came out of R. Durbin's group. They used FM-index derived from compressed
Burrows-Wheeler transform, and performed assembly of 1.2 billion sequence
reads from human genome with only 54GB of memory. Regular readers of our blog
know, how use of Burrows Wheeler transform dramatically improved speed of
sequence searching from MAQ-like programs to Bowtie/BWA-like program. It was a
matter of time, before someone tried the same method on assemblies instead of
searches.

3\. **Sequence-specific error profile of Illumina sequencers**

The archives of Velvet and Oases mailing lists have many interesting
discussions on how to improve efficiency of assembly runs, because everyone is
limited by RAM size and time. Pre-filtering of reads is one common theme
echoed by almost every expert, but apart from few reads with Ns and low-
complexity sequences, what can one reasonably filter out? An interesting paper
came out in Nucleic Acids Research from a Japanese group. It showed that NGS
reads from Illumina machines often contain sequence-specific errors near (i)
inverted repeats and (ii) GGC sequences. They observed this error profile in
all the Illumina sequencing data they examined regardless of the source
organisms or the sample preparation methods used.

These kinds of technology-dependent errors often confuse people as we can
recall from our experience. Several years back, we were working on tiling
array data and saw very strong signals in some unannotated genomic regions. We
tested those regions further using Northern blot hoping that they could be
novel non-coding RNA, but did not get any positive result. Later on, we
compared tiling array data from nine different organism and found out that T7
in vitro transcription system was a major source of artifact. You can read the
details
[here](http://www.febsletters.org/article/S0014-5793\(07\)00681-3/abstract).

4\. **Trinity - color space**

Several of you gave me feedback on the color space modification of Trinity
that we developed, and the results are no different from what we experienced
and reported earlier. The number of assembled transcripts were too few
compared to what one would expect in a comparable organism and what one often
gets from nucleotide space transcriptome assemblers. The reason, we suspect,
is higher noise level in color space data. This is a topic we plan to
investigate further after completing the genome assembly algorithm that we are
working on.

