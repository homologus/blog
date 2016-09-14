---
title: Minimizer Success - Disk-based Genome Sequencing Data Compression
tags: []
categories:
- blog
---
In [2014 The Year of Minimizers in
Bioinformatics](http://www.homolog.us/blogs/blog/2014/04/06/2014-the-year-of-
minimizers-in-bioinformatics/), we covered a number of applications of
minimizers and more keep coming. Readers will enjoy this newly posted paper in
arxiv.
<!--more-->

[Disk-based genome sequencing data
compression](http://arxiv.org/abs/1405.6874)

> We propose ORCOM (Overlapping Reads COmpression with Minimizers), a
compression algorithm dedicated to sequencing reads (DNA only). Most
compressors for such data, usually in FASTQ format, cannot efficiently
compress the DNA stream if a given dataset is large, since the redundancy
between overlapping reads cannot be easily exploited in the main memory, often
a few times smaller than the amount of data to compress. More interesting
solutions for this problem are disk-based~\cite{Y2011,CBJR2012}, where the
better of these two, from Cox~et al.~\cite{CBJR2012}, is based on the Burrows
--Wheeler transform (BWT) and achieves 0.484\,bits per base for a 135.3\,Gbp
human genome sequencing collection with 45-fold coverage. Our method makes use
of a conceptually simple and easily parallelizable idea of minimizers, to
obtain 0.376\,bits per base as the compression ratio.

Edit.

and our nameless blog gets cited too !

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/05/Capture9-300x102.png)

