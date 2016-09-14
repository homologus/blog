---
title: Benchmark Analysis of RNA-Seq is an Excellent Confirmation of 'Short Read'
  Noise
categories:
- rnaseq
---
In the past, we talked about 'short read noise', which is the noise introduced
by clean short reads due to being short. Readers may take at these two of our
earlier commentaries for details.
<!--more-->

[End of Short-Read Era? (Part I)](http://www.homolog.us/blogs/blog/2013/09/21
/end-illumina-era/)

[End of Short-Read Era? (Part II)](http://www.homolog.us/blogs/blog/2013/09/22
/end-short-read-era-part-ii/)

An excellent [biorxiv
paper](http://biorxiv.org/content/early/2014/07/14/007088.full-text.pdf+html)
analyzing RNA-seq assemblies provides substance to the above observations. Let
us jump straight to their conclusion, which has the strongest statements.

> This problem is fundamental and virtually all RNA-Seq investigators desire
to do their analysis cleanly at the transcript level. However, short reads
fundamentally lack the information necessary to build local information into
globally accurate transcripts. The strong desire of the community is what has
made it possible for several algorithms to gain widespread use in spite of the
apparent impossibility of a clean solution to date. This underscores the
importance of more research into this problem. Most likely it a satisfactory
solution will involve an evolution in the nature of the data. Or perhaps some
keen insight into how to identify and effectively utilize signals in the
genome that inform cellular machinery on what splice forms to generate

In fact, the authors are so flummoxed and bothered by the quality of
assemblies from short reads, they did not end the conclusion section with a
period.

Abstract here -

> The advantages of RNA sequencing (RNA-Seq) suggest it will replace
microarrays for highly parallel gene expression analysis. For example, in
contrast to arrays, RNA-Seq is expected to be able to provide accurate
identification and quantification of full-length transcripts. A number of
methods have been developed for this purpose, but short error prone reads
makes it a difficult problem in practice. It is essential to determine which
algorithms perform best, and where and why they fail. However, there is a
dearth of independent and unbiased benchmarking studies of these algorithms.
Here we take an approach using both simulated and experimental benchmark data
to evaluate their accuracy. We conclude that most methods are inaccurate even
using idealized data, and that no is method sufficiently accurate once
complicating factors such as polymorphisms, intron signal, sequencing error,
and multiple splice forms are present. These results point to the pressing
need for further algorithm development.

