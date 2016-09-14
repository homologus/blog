---
title: GPU-Accelerated BWT Construction for Large Collection of Short Reads
tags: []
categories:
- blog
---
[This](http://arxiv.org/abs/1401.7457) new preprint from Chi-Man Liu, Ruibang
Luo and Tak-Wah Lam is worth checking out (h/t: @lexnederbragt) !! BWT
construction is a major problem for large NGS read files, and as we discussed
in ["What Problems are Being Solved by the Top NGS Bioinformaticians
Today?"](http://www.homolog.us/blogs/blog/2013/11/18/problems-leading-
bioinformaticians-solving-today/), almost every top bioinformatician has a
BWT-construction project going on. There are several benefits of turning read
files into BWT quickly.
<!--more-->

(i) faster compression and easy transfer (Tony Cox's rearranging of reads is a
good example),

(ii) quick search through a large set of reads,

(iii) k-mer counting is an equivalent problem as BWT construction (see - ["BWT
Construction and K-mer Counting"](http://www.homolog.us/blogs/blog/2014/01/15
/bwt-construction-k-mer-counting/)),

(iv) genome assembly using SGA-type of algorithm.

We have not seen too many discussions of BWT construction in parallel, and
therefore look forward to going through this paper in detail. Their super-
duper CX1 parallel algorithm is shown in the image below (click to expand). On
first impression, it seems to have similarity with Lyndon word-based
constructions ([here](http://www.homolog.us/blogs/blog/2013/08/07/lyndon-word-
and-lyndon-factorization/) and
[here](http://www.homolog.us/blogs/blog/2013/08/24/going-through-the-lyndom-
word-paper/)), because the word is broken into smaller pieces of increasing
order.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/01/Capture4-300x266.png)

**Full abstract:**

> Advances in DNA sequencing technology have stimulated the development of
algorithms and tools for processing very large collections of short strings
(reads). Short-read alignment and assembly are among the most well-studied
problems. Many state-of-the-art aligners, at their core, have used the
Burrows-Wheeler transform (BWT) as a main-memory index of a reference genome
(typical example, NCBI human genome). Recently, BWT has also found its use in
string-graph assembly, for indexing the reads (i.e., raw data from DNA
sequencers). In a typical data set, the volume of reads is tens of times of
the sequenced genome and can be up to 100 Gigabases. Note that a reference
genome is relatively stable and computing the index is not a frequent task.
For reads, the index has to computed from scratch for each given input. The
ability of efficient BWT construction becomes a much bigger concern than
before. In this paper, we present a practical method called CX1 for
constructing the BWT of very large string collections. CX1 is the first tool
that can take advantage of the parallelism given by a graphics processing unit
(GPU, a relative cheap device providing a thousand or more primitive cores),
as well as simultaneously the parallelism from a multi-core CPU and more
interestingly, from a cluster of GPU-enabled nodes. Using CX1, the BWT of a
short-read collection of up to 100 Gigabases can be constructed in less than 2
hours using a machine equipped with a quad-core CPU and a GPU, or in about 43
minutes using a cluster with 4 such machines (the speedup is almost linear
after excluding the first 16 minutes for loading the reads from the hard
disk). The previously fastest tool BRC is measured to take 12 hours to process
100 Gigabases on one machine; it is non-trivial how BRC can be parallelized to
take advantage a cluster of machines, let alone GPUs.

\-----------------------------------------------------------------------

Relevant twitter comments -

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2014/01/Capture21-300x75.png)

Nick is referring to BarraCUDA project, but iirc, it is a mapping project
similar to SOAP3-dp and not BWT index generation.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/01/Capture5-300x117.png)

