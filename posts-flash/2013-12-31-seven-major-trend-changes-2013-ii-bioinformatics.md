---
title: Seven Major Trend Changes of 2013 - (ii) Bioinformatics
tags: []
categories:
- blog
---
**2\. In NGS Bioinformatics, SPAdes Assembler, BCR Algorithm and Diginorm Approach Gained Prominence**
<!--more-->

**a) SPAdes and Scaffolding Problem**

Velvet was all the rage in 2012, when we first reported about SPAdes from
Russia's Algorithmic Biology lab (Check
[here](http://www.homolog.us/blogs/blog/2012/09/12/from-de-bruijn-graphs-to-
rectangle-graphs-for-genome-assembly/),
[here](http://www.homolog.us/blogs/blog/2012/09/17/few-thoughts-on-spades-
papers/) and [here](http://www.homolog.us/blogs/blog/2012/10/01/heads-up-for-
readers-spades-vs-ray-benchmarking-is-done/)). One year later, SPAdes gained
recognition by [performing well in the GAGE-B
evaluation](http://www.homolog.us/blogs/blog/2013/05/20/spades-and-masurca-
assemblers-performed-best-in-gage-b-evaluation/).

In this respect, the biggest change in perception had been the realization
that scaffolding was a non-trivial step adding to most assembly errors.
Authors of SPAdes assembler spent considerable intellectual fire power to
solve the scaffolding problem.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/12/Capture11-300x53.png)

We wrote several commentaries on other excellent assemblers or on assembly-
related issues. A small subset is here.

[SPAdes and MaSuRCA Assemblers Performed Best in GAGE-B
Evaluation](http://www.homolog.us/blogs/blog/2013/05/20/spades-and-masurca-
assemblers-performed-best-in-gage-b-evaluation/)

[Our First Look at SOAPdenovo2 Source
Code](http://www.homolog.us/blogs/blog/2012/12/28/our-first-look-at-
soapdenovo2-source-code/)

[On MaSuRCA Paper and Algorithm](http://www.homolog.us/blogs/blog/2013/07/11
/enjoy-polish-dance/)

[Cleverness of the Ray Assembler](http://www.homolog.us/blogs/blog/2013/07/09
/cleverness-of-ray-assembler/)

[Very Helpful Preprocessing Module for Those Interested in Assembling
Genomes](http://www.homolog.us/blogs/blog/2013/07/02/cool-preprocessing-model-
for-genome-assembly/)

[Rayan Chikhis KmerGenie Slides from HitSeq
2013](http://www.homolog.us/blogs/blog/2013/07/22/rayan-chikhis-kmergenie-
slides-from-hitseq-2013/)

[GAM-NGS and REAPR Papers are
Published](http://www.homolog.us/blogs/blog/2013/05/29/gam-ngs-genomic-
assemblies-merger-for-next-generation-sequencing/)

\------------------------------------------------

**b) Alternate Approaches for Processing Large Libraries - Bauer-Cox-Rosone Algorithm/BEETL/Ropebwt and Kmer Counting/Diginorm/Sailfish**

Heng Li brought our attention to a series of excellent papers written by
Anthony Cox, Giovanna Rosone and co-authors in 2012. In "[Heng Li Releases
Ropebwt2](http://www.homolog.us/blogs/blog/2013/10/27/heng-li-releases-
ropebwt2/)", we wrote -

> We discussed BCR algorithm and related topics on BWT construction from short
reads many times ([here - check comment
section](http://www.homolog.us/blogs/blog/2013/05/14/external-memory-
generalized-suffix-and-lcp-arrays-construction/),
[here](http://www.homolog.us/blogs/blog/2013/08/14/a-constant-space-
comparison-based-algorithm-for-computing-the-burrows-wheeler-transform/),
[here](http://www.homolog.us/blogs/blog/2013/07/20/bioinformatics-patents-on-
burrows-wheeler-transform/) and
[here](http://www.homolog.us/blogs/blog/2013/08/07/lyndon-word-and-lyndon-
factorization/)). Readers may find [the following
implementation](https://github.com/lh3/ropebwt2) useful (h/t: @rayanchikhi).
Version 1 of this code is an important component of SGA assembler.

The goal of their work was to improve the processing of large NGS files by
converting them into FM index. When we checked ["the problems being solved by
the top NGS bioinformaticians
today?"](http://www.homolog.us/blogs/blog/2013/11/18/problems-leading-
bioinformaticians-solving-today/) in Nov 2013, we found that most had a
project related to implementation of similar algorithm. That definitely
qualifies as a change in perception, and it is driven by the large sizes of
HiSeq libraries and the time it takes to compress/process/ftp them.

Titus Brown and other researchers followed a different approach to solve the
same problem of large libraries. They converted each read into k-mer units and
used the k-mer collection as a substitute for the reads to expedite
processing. [Digital
normalization](http://www.homolog.us/blogs/blog/2012/04/02/digital-
normalization-from-c-titus-brown/) used k-mers to prune the read collection,
[Sailfish](http://www.homolog.us/blogs/blog/2013/08/28/deseq-and-sailfish-
papers/) used them to rapidly compute expression from RNAseq data without
alignment and [kSNP](http://www.homolog.us/blogs/blog/2013/12/10/ksnp/) used
k-mers to find SNPs without alignment. For k-mer counting, programs like
Jellyfish are popular, but readers may take a look at the following low-memory
methods from Rayan Chikhi and Titus Brown.

[DSK: K-mer Counting with Very Low Memory
Usage](http://www.homolog.us/blogs/blog/2013/02/06/dsk-k-mer-counting-with-
very-low-memory-usage/)

[Efficient Online k-mer Counting using a Probabilistic Data
Structure](http://www.homolog.us/blogs/blog/2013/09/13/efficient-online-k-mer-
counting-using-probabilistic-data-structure/)

What has not been generally recognized is that k-mer counting and building BWT
are equivalent approaches. In fact, one can easily build the Burrows Wheeler
transform of a large library by starting from its k-mer counts.

\----------------------------------------------------------

Speaking of blogs on algorithms, here is an incomplete list of several
excellent ones -

[Alex Bowe's Blog](http://alexbowe.com/)

[Heng Li's Blog](http://attractivechaos.wordpress.com/)

We will soon add a few others to the above list.

\-------------------------------------------------------

In the following commentary, we will cover -

[Seven Major Trend Changes of 2013 (iii) Genomics
](http://www.homolog.us/blogs/blog/2013/12/31/seven-major-trend-changes-2013
-iii-genomics/)

