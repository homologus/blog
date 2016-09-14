---
title: Going Through the Code of SOAPdenovo-trans
tags: []
categories:
- rnaseq
---
[We wrote earlier](http://www.homolog.us/blogs/blog/2013/05/30/soapdenovo-
trans-paper-shows-the-complexity-of-transcriptome-assembly/) about SOAPdenovo-
trans - BGI's [highly efficient](http://www.homolog.us/blogs/blog/2013/05/30
/soapdenovo-trans-paper-shows-the-complexity-of-transcriptome-assembly/)
assembler for transcriptomes (RNAseq). Its source-code had been available in
sourceforge for several months, but we did not get time to look at it yet.
<!--more-->

Last year, we worked through the code of SOAPdenovo2 genome assembler and you
can find the details in the following blog posts.

[Should SOAPdenovo2 Source Code be Made
Public?](http://www.homolog.us/blogs/blog/2012/12/27/should-soapdenovo2
-source-code-be-made-public/)

[Our First Look at SOAPdenovo2 Source
Code](http://www.homolog.us/blogs/blog/2012/12/28/our-first-look-at-
soapdenovo2-source-code/)

[January is Our Learn How SOAPdenovo2 Works
Month](http://www.homolog.us/blogs/blog/2013/01/01/january-is-our-learn-how-
soapdenovo2-works-month/)

[SOAPdenovo2 Demystified part
1](http://www.homolog.us/blogs/blog/2013/01/05/soapdenovo2-demystified-
part-1/)

[SOAPdenovo2 Demystified part
(a)](http://www.homolog.us/blogs/blog/2013/01/05/soapdenovo2-demystified-
part-a/)

[SOAPdenovo2 Demystified part (b) [multi-thread
implementations]](http://www.homolog.us/blogs/blog/2013/01/27/soapdenovo2
-demystified-part-b-multi-thread-implementations/)

[SOAPdenovo2 Demystified A Rough Guideline of Functionality](http://www.homolo
g.us/blogs/blog/2013/02/05/soapdenovo2-demystified-a-rough-guideline-of-
functionality/)

Today we are starting to use our previous knowledge of the genome assembler to
start understanding BGI's transcriptome assembler. This post gives a
preliminary overview of the main files, and as we get a better grasp of the
code, we will continue with additional blog posts.

It appears to us that SOAPdenovo2 and SOAPdenovo-trans share a large part of
the code-bases. The differences are listed below.

The following files are used by SOAPdenovo2 (the genome assembler), but not
the transcriptome assembler.

> cutTip_graph2.c (500 lines), iterate.c (2510 lines), kmerhash.c (540 lines),
linearEdge.c (429 lines), read2edge.c (1612 lines)

The following files were written for SOAPdenovo-trans only and were not
present in SOAPdenovo2.

> loadReadPath.c (118 lines), ReadTrace.c (160 lines), sortContig.c (388
lines), transcriptome.c (2350 lines)

What is going on?

As it appears to us, the **orderContig.c** (largest file in SOAPdenovo2) is
split into two and is used to write **transcriptome.c** in the transcriptome
assembler. Also, parts of iterate.c (second largest file in SOAPdenovo2) is
copies into sortContig.c and the rest are ditched. We compared the sizes of
other files and find them nearly similar. Therefore, the files mentioned above
are the most important additions, if someone wants to understand the code.

\---------------------------------------------------------

How does the transcriptome assembler run so fast? The answer is not very
different from BGI's genome assembler, because the multi-threaded
implementation is borrowed fully from SOAPdenovo2. Moreover, [using pthreads
instead of openMP](http://www.homolog.us/blogs/software/2013/08/04/pthreads-
or-openmp/) allows SOAPdenovo2 to do fine-grained engineering of the code. It
is interesting that BGI and Heng Li both write their codes in C. Maybe they
figured out the evil plot by Stroustoup :)

[Why Was C++ Created? A Secret Interview with Bjarne
Stroustrup](http://www.homolog.us/blogs/software/2014/02/01/c-created-secret-
interview-bjarne-stroustrup/)

We will add more on SOAPdenovo-trans as we work through the code.

