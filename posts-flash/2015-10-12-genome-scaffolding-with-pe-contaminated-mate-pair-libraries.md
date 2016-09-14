---
title: Genome scaffolding with PE-contaminated mate-pair libraries
tags: []
categories:
- blog
---
If Rayan Chikhi is involved, it has to be a good paper.
<!--more-->

[Link](http://biorxiv.org/content/early/2015/08/28/025650)

> Scaffolding is often an essential step in a genome assembly process,in which
contigs are ordered and oriented using read pairs from a combination of
paired-ends libraries and longer-range mate-pair libraries. Although a simple
idea, scaffolding is unfortunately hard to get right in practice. One source
of problem is so-called PE-contamination in mate-pair libraries, in which a
non-negligible fraction of the read pairs get the wrong orientation and a much
smaller insert size than what is expected. This contamination has been
discussed in previous work on integrated scaffolders in end-to-end assemblers
such as Allpaths-LG and MaSuRCA but the methods relies on the fact that the
orientation is observable, \emph{e.g.}, by finding the junction adapter
sequence in the reads. This is not always the case, making orientation and
insert size of a read pair stochastic. Furthermore, work on modeling PE-
contamination has so far been disregarded in stand-alone scaffolders and the
effect that PE-contamination has on scaffolding quality has not been examined
before. We have addressed PE-contamination in an update of our scaffolder
BESST. We formulate the problem as an Integer Linear Program (ILP) and use
characteristics of the problem, such as contig lengths and insert size, to
efficiently solve the ILP using a linear amount (with respect to the number of
contigs) of Linear Programs. Our results show significant improvement over
both integrated and standalone scaffolders. The impact of modeling PE-
contamination is quantified by comparison with the previous BESST model. We
also show how other scaffolders are vulnerable to PE-contaminated libraries,
resulting in increased number of misassemblies, more conservative scaffolding,
and inflated assembly sizes. The model is implemented in BESST. Source code
and usage instructions are found at https://github.com/ksahlin/BESST. BESST
can also be downloaded using PyPI.

