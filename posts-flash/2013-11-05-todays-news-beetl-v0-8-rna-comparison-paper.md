---
title: Today&#039;s News - BEETL v0.8 Release and RNA Comparison Papers
tags: []
categories:
- rnaseq
---
Tony Cox posted -
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/11/Capture1-300x66.png)

It is an implementation of Bauer-Cox-Rosone algorithm mentioned in our blog
several times. [Heng Li's ropebwt](http://www.homolog.us/blogs/blog/2013/10/27
/heng-li-releases-ropebwt2/) is another implementation. Readers are encouraged
to check the [BEETL website](http://beetl.github.io/BEETL/).

> **Release History**

**Version 0.8.0 (29th October 2013)**

New BWT-based tumour-normal filter (see example in doc/BEETL.md)

Beetl-compare modes: 'split' renamed to 'splice'

Beetl-compare modes: new 'tumour-normal'

16-way parallel beetl-compare

MetaBEETL is now able to run without sequence propagation (which is faster)

Upgraded requirement: autoconf 2.65 (improved regression testing)

**Version 0.7.0 (18th September 2013)**

New beetl-correct tool

Updated regression tests

Detection of required libraries and OpenMP in configure script

**Version 0.6.0 (27th August 2013) 

**

Important: Harmonised file encodings - you may need to rebuild your BWT files
or just convert bwt-B00 from BWT_ASCII to BWT_RLE with beetl-convert (bwt-B00
was always ASCII-encoded. It now follows the same encoding as the other piles)

Now requires GCC with C++11 support (gcc 4.3 or above)

New Markdown documentation style

Faster beetl-compare and metaBEETL

Lossless quality compression scripts added, even though they are not using BWT

New features:

BWT creation with reverse-complemented reads (--add-rev-comp)

BWT creation with multiple reads per sequence (--sequence-length)

Support for BCL and BCL.gz in beetl-convert

Here is the last BCR-related paper mentioned in their website -

[Adaptive reference-free compression of sequence quality
scores](http://arxiv.org/abs/1305.0159)

> Rapid technological progress in DNA sequencing has stimulated interest in
compressing the vast datasets that are now routinely produced. Relatively
little attention has been paid to compressing the quality scores that are
assigned to each sequence, even though these scores may be harder to compress
than the sequences themselves. By aggregating a set of reads into a compressed
index, we find that the majority of bases can be predicted from the sequence
of bases that are adjacent to them and hence are likely to be less informative
for variant calling or other applications. The quality scores for such bases
are aggressively compressed, leaving a relatively small number at full
resolution. Since our approach relies directly on redundancy present in the
reads, it does not need a reference sequence and is therefore applicable to
data from metagenomics and de novo experiments as well as to resequencing
data.

Results:

We show that a conservative smoothing strategy affecting 75% of the quality
scores above Q2 leads to an overall quality score compression of 1 bit per
value with a negligible effect on variant calling. A compression of 0.68 bit
per quality value is achieved using a more aggressive smoothing strategy,
again with a very small effect on variant calling.

\-------------------------------------------------------------------------

Those working on RNAseq may find the following papers helpful (h/t:
@genetics_blog).

[Assessment of transcript reconstruction methods for RNA-
seq](http://www.nature.com/nmeth/journal/vaop/ncurrent/full/nmeth.2714.html)

> We evaluated 25 protocol variants of 14 independent computational methods
for exon identification, transcript reconstruction and expression-level
quantification from RNA-seq data. Our results show that most algorithms are
able to identify discrete transcript components with high success rates but
that assembly of complete isoform structures poses a major challenge even when
all constituent elements are identified. Expression-level estimates also
varied widely across methods, even when based on similar transcript models.
Consequently, the complexity of higher eukaryotic genomes imposes severe
limitations on transcript recall and splice product discrimination that are
likely to remain limiting factors for the analysis of current-generation RNA-
seq data.

[Optimizing de novo assembly of short-read RNA-seq data for
phylogenomics](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3663818/)

[Computational analysis of bacterial RNA-Seq
data](http://www.ncbi.nlm.nih.gov/pubmed/23716638)

Speaking of comparison between RNAseq methods, @lpachter mentioned:

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/11/Capture3-300x64.png)

Why is everyone after FluxCapacitor? Here is why. In a way that advertisers
play with words to create marketing slogans (long list
[here](http://www.hongkiat.com/blog/77-catchy-and-creative-slogans/)), GTEx
played with the word deep (usually used with 'deep sequencing') in their
abstract. We highlighted two instances below.

![Capture1](http://www.homolog.us/blogs/wp-
content/uploads/2013/11/Capture11-300x137.png)

Therefore, just like when Google uses 'don't be evil' as marketing slogan,
people search for evil acts by Google, the words 'deep analysis' and 'deep
understanding' are being challenged here.

The cover letter for GTEx claims that they characterize variations with
'higher precision than ever before'. How correct is that? Also, why is 'higher
precision than ever before' important, but not accuracy?

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/11/Capture21-300x255.png)

Also, the word 'functional' is elevated from ENCODE's abstract to their title.
Do they really 'uncover' 'functional' variations? What are their functions?

[Transcriptome and genome sequencing uncovers functional variation in
humans](http://www.nature.com/nature/journal/v501/n7468/full/nature12531.html)

