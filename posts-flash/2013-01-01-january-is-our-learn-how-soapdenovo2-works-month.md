---
title: January is Our 'Learn How SOAPdenovo2 Works' Month
tags: []
categories:
- blog
---
We have strong interest in learning how various genome and transcriptome
assemblers work, and SOAPdenovo2, being a cutting edge genome assembler, peeks
our interest. Few days back, we [started parsing through the source
code](http://www.homolog.us/blogs/2012/12/28/our-first-look-at-soapdenovo2
-source-code/), but, based on excellent suggestion of Rayan, we decided to set
up a wiki to learn and write about the code. Here is the [top wiki
page](http://homolog.us/wiki1/index.php?title=SOAPdenovo2) for SOAPdenovo,
which replicates the blog commentary about various source files. We also set
up a page for each source file and listed all its functions. For example, the
functions of stack.c are shown
[here](http://homolog.us/wiki1/index.php?title=SOAPdenovo2:stack.c). You can
find other files by replacing 'stack.c' in the title with the name of the file
of interest.
<!--more-->

**Our expectations:**

1\. We love digging into other people's codes, because only by going through
the code as well as reading written description of the algorithm, one can gain
confidence about understanding a program. Studying the algorithm alone is
often not enough, especially if you want to re-implement it or modify existing
code-base. Reading the code without knowledge of algorithm is often hopeless.

2\. In the past, we studied various other bioinformatics codes, and the method
was to print out important files, manually go through each function, write
notes on the margin, etc. The method works, but we often tend to lose those
old papers or forget their significance. This is the first time we are using
the wiki approach. Hopefully that will help us retain our notes, but whether
our learning process improves remains to be seen.

3\. If the wiki method is useful, we will use it to look into other important
programs, such as Bowtie, Velvet, Trinity, etc. We often receive questions on
how one or other steps of Velvet works, and realized that having annotated
wiki pages for source files would help us direct readers to those pages.

**How the community may benefit:**

1\. Many bioinformatics students are taking classes on algorithms related to
next-gen sequencing, de Bruijn graphs, genome assembly, etc. Nothing can speed
up the learning process more than going under the hood of a functional code
and twisting its nuts and bolts.

2\. Given how well SOAPdenovo works for genome assembly, many researchers may
also benefit from parsing its code.

3\. In future, we expect to modify parts of SOAPdenovo code to add other
functionality, or borrow modules from SOAPdenovo into other assemblers. That
may potentially be beneficial for BGI as well.

We will continue to play with the code and modify the wiki page. Right now, we
are focusing on the following files - (kmer.c, prlHashReads.c, readseq1by1.c,
prlRead2Ctg.c, prlRead2path.c, read2edge.c, prlReadFillGap.c, localAsm.c,
bubble.c, iterate.c, **orderContig.c**, dfib.c, fib.c), and their wiki pages
will be updated as we make progress. Among those, **orderContig.c** is the
most important. A new blog commentary on SOAPdenovo2 will be posted, only if
we make any major leap in understanding.

