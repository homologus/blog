---
title: 'MICA: A fast short-read aligner that takes Full Advantage of Intel Many Integrated
  Core Architecture (MIC)'
tags: []
categories:
- blog
---
This paper was posted in arxiv in early 2014, but we forgot to mention here.
Ruibang Luo (one of the authors) mentioned that the paper is now accepted.
<!--more-->

[Link](http://arxiv.org/abs/1402.4876)

> Background: Short-read aligners have recently gained a lot of speed by
exploiting the massive parallelism of GPU. An uprising alternative to GPU is
Intel MIC; supercomputers like Tianhe-2, currently top of TOP500, is built
with 48,000 MIC boards to offer ~55 PFLOPS. The CPU-like architecture of MIC
allows CPU-based software to be parallelized easily; however, the performance
is often inferior to GPU counterparts as an MIC board contains only ~60 cores
(while a GPU board typically has over a thousand cores). Results: To better
utilize MIC-enabled computers for NGS data analysis, we developed a new short-
read aligner MICA that is optimized in view of MICs limitation and the extra
parallelism inside each MIC core. Experiments on aligning 150bp paired-end
reads show that MICA using one MIC board is 4.9 times faster than the BWA-MEM
(using 6-core of a top-end CPU), and slightly faster than SOAP3-dp (using a
GPU). Furthermore, MICAs simplicity allows very efficient scale-up when
multiple MIC boards are used in a node (3 cards give a 14.1-fold speedup over
BWA-MEM). Summary: MICA can be readily used by MIC-enabled supercomputers for
production purpose. We have tested MICA on Tianhe-2 with 90 WGS samples (17.47
Tera-bases), which can be aligned in an hour less than 400 nodes. MICA has
impressive performance even though the current MIC is at its initial stage of
development (the next generation of MIC has been announced to release in late
2014).

