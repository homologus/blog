---
title: 'SOAP3-dp: Fast, Accurate and Sensitive GPU-Based Short Read Aligner'
tags: []
categories:
- blog
---
**Abstract:**
<!--more-->

> To tackle the exponentially increasing throughput of Next-Generation
Sequencing (NGS), most of the existing short-read aligners can be configured
to favor speed in trade of accuracy and sensitivity. SOAP3-dp, through
leveraging the computational power of both CPU and GPU with optimized
algorithms, delivers high speed and sensitivity simultaneously. Compared with
widely adopted aligners including BWA, Bowtie2, SeqAlto, CUSHAW2, GEM and GPU-
based aligners BarraCUDA and CUSHAW, SOAP3-dp was found to be two to tens of
times faster, while maintaining the highest sensitivity and lowest false
discovery rate (FDR) on Illumina reads with different lengths. Transcending
its predecessor SOAP3, which does not allow gapped alignment, SOAP3-dp by
default tolerates alignment similarity as low as 60%. Real data evaluation
using human genome demonstrates SOAP3-dp's power to enable more authentic
variants and longer Indels to be discovered. Fosmid sequencing shows a 9.1%
FDR on newly discovered deletions. SOAP3-dp natively supports BAM file format
and provides the same scoring scheme as BWA, which enables it to be integrated
into existing analysis pipelines. SOAP3-dp has been deployed on Amazon-EC2,
NIH-Biowulf and Tianhe-1A.

[View paper at PLOS One](http://www.plosone.org/article/info%3Adoi%2F10.1371%2
Fjournal.pone.0065632)

\--------------------------------

Ruibang requested us to write something original on the paper. We [already
covered the core algorithm](http://www.homolog.us/blogs/blog/2013/06/01/bi-
directional-bwt-or-2-way-bwt-2bwt/) without going into details, and would like
to explore the GPU code and write here after he uploads it. Until then, why
not have pictures of few authors so that you can recognize them at
conferences? :)

**Ruibang Luo:**

![](http://seq.cbrc.jp/ISCB-Asia2012/sessions/photos/RuibangLuo.jpg)

**Hing Fung Ting:**

![](http://hub.hku.hk/researcherimage/rp00177)

**Shaoliang Peng:**

![](http://www.icg-europe.org/_upload/news/2013-04-17/5d0337e4-f57b-4c1a-
8b82-49aeb3cd21f7.jpg)

**Yingrui Li:**

![](http://www.icgamericas.org/Yingrui_Li.jpg)

**Ruiqiang Li:**

![](http://www.cls.edu.cn/uploads/Boosen1323416259.jpg)

**Tak-Wah Lam:**

![](http://i.cs.hku.hk/~twlam/index_files/image002.jpg)

