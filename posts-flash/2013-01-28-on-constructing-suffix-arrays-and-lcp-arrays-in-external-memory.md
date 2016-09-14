---
title: On Constructing Suffix Arrays and LCP Arrays in External Memory
tags: []
categories:
- blog
---
In a [previous commentary](http://www.homolog.us/blogs/2013/01/21/lightweight-
bwt-construction-for-very-large-string-collections/), we asked readers about
the state of the art regarding construction of suffix arrays in external
memory, and Felipe Louza pointed us to a [very good recent
paper](http://panthema.net/2012/1119-eSAIS-Inducing-Suffix-and-LCP-Arrays-in-
External-Memory/alenex13esais.pdf).
<!--more-->

**Inducing Suffix and LCP Arrays in External Memory**

Timo Bingmann, Johannes Fischery, and Vitaly Osipovz

> We consider text index construction in external memory (EM). Our first
contribution is an inducing algorithm for suffix arrays in external memory.
Practical tests show that this outperforms the previous best EM sufix sorter
[Dementiev et al., ALENEX 2005] by a factor of about two in time and
I/O-volume. Our second contribution is to augment the first algorithm to also
construct the array of longest common prfie xes (LCPs). This yields the first
EM construction algorithm for LCP arrays. The overhead in time and I/O volume
for this extended algorithm over plain suffix array construction is roughly
two. Our algorithms scale far beyond problem sizes previously considered in
the literature (text size of 80 GiB using only 4 GiB of RAM in our
experiments).

Too difficult? Please try [these slides](http://panthema.net/2012/1119-eSAIS-
Inducing-Suffix-and-LCP-Arrays-in-External-Memory/alenex13esais-slides.pdf)
then. [Here is author's website](http://panthema.net/2012/1119-eSAIS-Inducing-
Suffix-and-LCP-Arrays-in-External-Memory/) for more information
and.........,you guessed it, the source code.

Many thanks Felipe !! We are cutting and pasting his helpful comment below.

> Hi, about this issue, recently at ALENEX 2013 was published a new method to
construct SA and also construct the LCP array in external memory, the eSAIS
algorithm [Bingmann et al, 2013] is based on the best internal memory
algorithm SAIS [Nong et al, 2009] (which libdivsufsort implements).

The authors reported that eSAIS outperforms DC3-disk [Dementiev, 2005] by a
factor of 2-3 in time.

link: http://panthema.net/2012/1119-eSAIS-Inducing-Suffix-and-LCP-Arrays-in-
External-Memory/alenex13esais.pdf

\-------------------

For a quick recap on why anyone should care, search algorithms like BWA,
Bowtie and SOAP2 require Burrows Wheeler Transform index construction of the
genome. Even though BWA needs only 2-3GB of RAM to search within human genome,
the amount of RAM to construct BWT index is much higher. That means one may
need to use non-RAM methods for index construction.

Innovative genome assembly algorithms like [string graph
assemblers](http://www.homolog.us/blogs/category/string-graph-assembler/) also
rely on Burrows Wheeler Transform. So, our problem is not limited to search
algorithms only. String graph assembler (SGA) performed the best in assembling
snake genome in [the Assemblathon-2
contest](http://www.homolog.us/blogs/2013/01/23/assemblathon-2-paper-is-
available-at-arxiv/). Also note that when it comes to Illumina reads of
constant length, [SGA already found a highly efficient memory-based
method](http://www.homolog.us/blogs/2013/01/21/lightweight-bwt-construction-
for-very-large-string-collections/) of index construction.

\---------------

Edit. A follow up commentary is [posted
here](http://www.homolog.us/blogs/2013/02/21/construction-of-suffix-array-in-
external-memory-follow-up/).

