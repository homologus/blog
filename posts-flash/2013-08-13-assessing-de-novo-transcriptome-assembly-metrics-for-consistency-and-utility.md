---
title: Assessing De Novo Transcriptome Assembly Metrics for Consistency and Utility
tags: []
categories:
- rnaseq
---
[This paper](http://www.biomedcentral.com/content/pdf/1471-2164-14-465.pdf)
forwarded by @srbehera11 seems to be the right one for today, because we have
been trying to figure out the best way to compare Trinity and SOAPdenovo-trans
outputs for one of our fish transcriptome assemblies. The measures like high
N50 may not be meaningful for transcriptomes, because the assembled units are
do not always have to be big to be correct. It is possible that a
transcriptome assembler giving high N50 may have merged neighboring genes.
<!--more-->

> **Background**: Transcriptome sequencing and assembly represent a great
resource for the study of non-model species, and many metrics have been used
to evaluate and compare these assemblies. Unfortunately, it is still unclear
which of these metrics accurately reflect assembly quality.

**Results**: We simulated sequencing transcripts ofDrosophila melanogaster. By assembling these simulated reads using both a perfect and a modern transcriptome assembler while varying read length and sequencing depth, we evaluated quality metrics to determine whether they 1) revealed perfect assemblies to be of higher quality, and 2) revealed perfect assemblies to be more complete as data quantity increased. Several commonly used metrics were not consistent with these expectations, including average contig coverage and length, though they became consistent when singletons were included in the analysis. We found several annotation-based metrics to be consistent and informative, including contig reciprocal best hit count and contig unique annotation count. Finally, we evaluated a number of novel metrics such as reverse annotation count, contig collapse factor, and the ortholog hit ratio, discovering that each assess assembly quality in unique ways. 

**Conclusions**: Although much attention has been given to transcriptome assembly, little research has focused on determining how best to evaluate assemblies, particularly in light of the variety of options available for read length and sequencing depth. Our results provide an important review of these metrics and give researchers tools to produce the highest quality transcriptome assemblies.

Also, @rayanchikhi found out these slides related to the above paper that you
may find helpful. Please click on the image to view the pdf file.

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture29-300x176.png)

While on the topic, Ruibang Luo (@aquaskyline) informed us that SOAPdenovo-
trans paper at arxiv has been [updated two days back with an updated
version](http://arxiv.org/abs/1305.6760).

