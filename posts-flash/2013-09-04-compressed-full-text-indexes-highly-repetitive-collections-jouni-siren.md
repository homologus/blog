---
title: Compressed Full-Text Indexes for Highly Repetitive Collections (Jouni Sir&eacute;n)
tags: []
categories:
- blog
---
Readers may find GCSA framework mentioned by Paul Melsted useful. The context
is mapping of reads into an assembly graph and the results came from Jouni
Sirn's PhD thesis (available from the website).
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/09/Capture3-300x108.png)

[GCSA Website](http://www.cs.helsinki.fi/group/suds/gcsa/)

>

GCSA [2, 3] is a compressed suffix array for finite languages. The
implementation now supports general alphabet and multiple automata. The most
up-to-date description of GCSA can be found in [3].

See README in the package for further information.

The implementation is available for download under the MIT / X11 License. Our
implementation of RLCSA [1, 3] is required for compiling GCSA. (The current
version of GCSA should always work with the current version of RLCSA.)

Return to the SuDS homepage.

References

1\. Veli Mkinen, Gonzalo Navarro, Jouni Sirn, and Niko Vlimki: Storage and
Retrieval of Highly Repetitive Sequence Collections.

Journal of Computational Biology 17(3):281-308, 2010.

[Article] [Preprint]

2\. Jouni Sirn, Niko Vlimki, and Veli Mkinen: Indexing Finite Language
Representation of Population Genotypes.

Proc. WABI 2011, Springer LNCS 6833, pp. 270-281, Saarbrcken, Germany,
September 5-7, 2011.

[Article] [Preprint] [Full version]

3\. Jouni Sirn: Compressed Full-Text Indexes for Highly Repetitive Collections
(PhD Thesis).

Department of Computer Science, Series of Publications A, Report A-2012-5,
University of Helsinki, June 2012. [Thesis]

The second reference can be [downloaded from
here](http://arxiv.org/pdf/1010.2656v4.pdf).

**Indexing Finite Language Representation of Population Genotypes**

> Abstract. With the recent advances in DNA sequencing, it is now possible to
have complete genomes of individuals sequenced and assembled. This rich and
focused genotype information can be used to do diff erent population-wide
studies, now rst time directly on whole genome level. We propose a way to
index population genotype information together with the complete genome
sequence, so that one can use the index to eciently align a given sequence to
the genome with all plausible genotype recombinations taken into account. This
is achieved through converting a multiple alignment of individual genomes into
a nite automaton recognizing all strings that can be read from the alignment
by switching the sequence at any time. The nite automaton is indexed with an
extension of Burrows-Wheeler transform to allow pattern search inside the
plausible recombinant sequences. The size of the index stays limited, because
of the high similarity of individual genomes. The index fi nds applications in
variation calling and in primer design. On a variation calling experiment, we
found about 1.0% of matches to novel recombinants just with exact matching,
and up to 2.4% with approximate matching.

\-----------------------------------------------------

On a related topic, readers may look at

[Short Read Alignment with Populations of
Genomes](http://www.homolog.us/blogs/blog/2013/07/28/short-read-alignment-
with-populations-of-genomes/)

