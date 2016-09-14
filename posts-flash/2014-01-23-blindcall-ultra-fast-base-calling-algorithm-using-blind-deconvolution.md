---
title: 'BlindCall: Ultra-fast Base-calling Algorithm Using Blind Deconvolution'
tags: []
categories:
- blog
---
Edit. If you are looking for new nanopore company Quantum Biosciences, the
correct link is below (thanks Lex). We apologize for posting this wrong link
in twitter. The article on BlindCall is unrelated to Quantum Biosciences.
<!--more-->

[A New Nanoscale Sequencing Company Comes into Fray and Releases Data
!!](http://www.homolog.us/blogs/blog/2014/01/27/new-nanoscale-sequencing-
company-comes-fray-releases-data/)

\----------------------------------------------------------------------------

Chengxi Ye, who previously developed a memory-efficient de Bruijn assembly
algorithm ([Exploiting sparseness in de novo genome
assembly](http://www.biomedcentral.com/1471-2105/13/S6/S1)), worked on another
difficult problem of next-gen sequencing, namely base-calling. Speed is a big
problem for most newly proposed base-calling algorithms, but apparently his
Matlab implementation runs 10-1000x times faster than those other suggestions.
His algorithm incorporates ideas from many mathematical concepts -
convolution, image segmentation and even Google's pagerank algorithm, which is
known for its speed.

[BlindCall: Ultra-fast Base-calling of High-throughput Sequencing Data by
Blind Deconvolution ](http://bioinformatics.oxfordjournals.org/content/early/2
014/01/09/bioinformatics.btu010.full.pdf+html)

> Motivation: Base-calling of sequencing data produced by highthroughput

sequencing platforms is a fundamental process in current bioinformatics
analysis. However, existing third-party probabilistic or machine-learning
methods that significantly improve the accuracy of base-calls on these
platforms are impractical for production use due to their computational
inefficiency.

Results: We directly formulate base-calling as a blind deconvolution problem
and implemented BlindCall as an efficient solver to this inverse problem.
BlindCall produced base-calls at accuracy comparable to state-of-the-art
probabilistic methods while processing data at rates ten times faster in most
cases. The computational complexity of BlindCall scales linearly with read
length making it better suited for new long-read sequencing technologies.

Availability and Implementation: BlindCall is implemented as a set of Matlab
scripts available for download at http://cbcb.umd.edu/~hcorrada/secgen.

Email address available in paper.

To better understand the implications of his method, we asked him a few
questions. His detailed replies are presented below.

**Q1. What is the biggest problem in base-calling these days - speed or quality? You mention that existing tools are tool slow to be practical, but Illumina seems to already have a program in their machine. How do they do that?**

> CY: For most third party algorithms the biggest problem is the speed. Common
algorithms are usually too slow to be used in practice (10-1000x times
slower), whlie the accuracy is noticably better than Illumina's in-house base-
caller Bustard. Illumina's approach is using a simple probablistic (Markov)
model which is similar to most third party (but more complicated) approaches.
My guess is because of the simplicity and good implementation, illumina is
giving us good speed and reasonable quality. All these approaches are
parametric models and are basically estimating the pre-set parameters. As an
example, if they model the image blur, they will assume the blur kernel is a
fixed type (say gaussian) and use probablistic methods to estimate the
parameters of this gaussian model. In contrast, our method doesn't put any
restrictions and simply use a sparsity trick to estimate the general blur
kernel.

**Q2. How will your algorithm apply for, let's say, PacBio type long-read sequencers? 

Q3. Will it work for nanopore-type electrical signals?**

> CY: Hopefully the techniques we introduced are general and can be adapted to
several other platforms. But one major problem here is that sequencing
companies are doing too little (basically no paper/document at all!) to share
their signals so we have difficulty in learning what major problems they have.
A second problem is we need more cutting edge signal processing techniques to
fully understand and tackle the problems.

