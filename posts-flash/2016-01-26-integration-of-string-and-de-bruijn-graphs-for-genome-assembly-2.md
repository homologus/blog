---
title: Integration of String and de Bruijn Graphs for Genome Assembly
tags: []
categories:
- blog
---
Any thoughts?
<!--more-->

[Link](http://bioinformatics.oxfordjournals.org/content/early/2016/01/09/bioin
formatics.btw011.short?rss=1)

> Motivation: String and de Bruijn graphs are two graph models used by most
genome assemblers. At present, none of the existing assemblers clearly
outperforms the others across all datasets. We found that although a string
graph can make use of entire reads for resolving repeats, de Bruijn graphs can
naturally assemble through regions that are error-prone due to sequencing
bias.

Results: We developed a novel assembler called StriDe that has advantages of
both string and de Bruijn graphs. First, the reads are decomposed adaptively
only in error-prone regions. Second, each paired-end read is extended into a
long read directly using an FM-index. The decomposed and extended reads are
used to build an assembly graph. In addition, several essential components of
an assembler were designed or improved. The resulting assembler was fully
parallelized, tested, and compared with state-of-the-art assemblers using
benchmark datasets. The results indicate that contiguity of StriDe is
comparable with top assemblers on both short-read and long-read datasets, and
the assembly accuracy is high in comparison with the others.

Availability: https://github.com/ythuang0522/StriDe

Contact: ythuang@cs.ccu.edu.tw

