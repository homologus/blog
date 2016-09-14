---
title: What is Faster - CPU, GPU or FPGA? Our Investigation of Leading Alignment Algorithms
  - (i)
tags: []
categories:
- blog
---
Let us give the punchline so that impatient readers can move on to doing other
things. **The question - 'which technology among CPU, GPU and FPGA is faster'
- is too simplistic and cannot be easily answered.** The details will follow
in several commentaries.
<!--more-->

Over the last few days, we have been studying various alignment algorithms in
full depth (i.e. at the implementation level) to understand relative merits of
various hardware technologies. For GPU, we picked Ruibang's SOAP3-dp paper
[recently published in PLOS-One](http://www.plosone.org/article/info%3Adoi%2F1
0.1371%2Fjournal.pone.0065632#pone.0065632-Liu4). For CPU, we studied Heng
Li's [BWA-MEM paper](http://arxiv.org/abs/1303.3997) recently 'unpublished' in
arxiv. For FPGA, we chose
[Shepard](http://rcl.ece.iastate.edu/sites/default/files/papers/NelTow12A.pdf)
accepted in Proceedings of the International Conference on Formal Methods and
Models for Codesign (MEMOCODE), 2012. Also we carefully studied all relevant
earlier papers to understand where various algorithmic ideas came from. For
example, BWA-MEM paper provides very little details on the algorithm, whereas
[Heng Li's Fermi paper](http://bioinformatics.oxfordjournals.org/content/early
/2012/05/07/bioinformatics.bts280) covered them with gory details. We thank
Heng and Ruibang for kindly replying to our email questions, when we got
stuck.

Our discussion will constitute of several parts broken into multiple
commentaries. Roughly we will cover the following topics.

(i) [CPU vs GPU vs FPGA - a General Introduction of Three Technologies
](http://www.homolog.us/blogs/blog/2013/07/01/what-is-faster-cpu-gpu-or-fpga-
our-investigation-of-leading-alignment-algorithms-ii-2/)

> This commentary provides you with a general introduction of the three
hardware technologies without referring to any bioinformatics algorithm.

(ii) Philosophical Origin of Alignment Algorithms in BWA-MEM, SOAP3-dp and
Shepard

> We go into the details of three alignment algorithms and explain how the
choice of hardware technology affected the implementation

(iii) Comparison of Implementation Details

> This commentary includes back-of the-envelope comparison of speed, potential
future speed, bottlenecks, etc.

(iv) Other Factors Such as Code Availability, Upgrade and Commoditization

> If you want to play, do not forget that three worlds follow three different
sets of rules. We discuss them here.

(v) Summary of Comparison

> Sorry folks. You expected to hear terms like Burrows Wheeler transform,
indels and clock speed, but we have to leave you with jargons such as 'patent
right', 'engineering', 'business decision' and 'total cost of ownership'.

\------------------------------------

The above points will be covered in several forthcoming commentaries.

