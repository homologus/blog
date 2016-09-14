---
title: 'Cross-post: Is trimming beneficial for RNA-Seq??'
tags: []
categories:
- rnaseq
---
The following commentary is a cross-post from [MacManes Lab (Using genomics to
understand adaptation in non-model organisms)](http://genomebio.org/is-
trimming-is-beneficial-in-rna-seq/). In our own work, we try to avoid read-
trimming as much as possible, because the trimming process introduces an
additional arbitrary parameter in the assembly process, which is not needed.
The de Bruijn graph-based assembly process is supposed to take care of the
low-quality ends of reads in the 'tip removal' step. Someone inclined to do
read trimming should play with tip-removal parameters instead of trying to
find optimal quality for trimming.
<!--more-->

\-----------------------------------------------------------------------------
------
