---
title: From de Bruijn Graph to Minimal Promoter
tags: []
categories:
- blog
---
Another paper with similar theme as Mike White's got published today (h/t:
@genologos). The beauty of this work is their creative use of de Bruijn graphs
to come up with a compact set of nucleotides covering all possible k-mers
(k=6) as promoters. Quite surprisingly, they show few bindings of
transcription factors leading to GFP expression (27 out of 4096) as opposed to
ubiquitous binding in Mike White's paper. We do not know where exactly the
difference comes from, and requested Mike to help. BTW, where do people
download the supplements from for Genome Biology papers? We do not see any
link for supplementary materials on the sidebar.
<!--more-->

[Edit. There is no conflict between Mike White's finding and this one.
Firstly, the ratio 27 out of 4096 stated above is wrong and should be 27/184
as pointed out by Juan in comment section. Secondly, even after that we are
not sure whether that 27/184 is a fair comparison with the other paper,
because total length of promoter is different as well as the content. Finally,
this paper does GFP measurement, whereas Mike measured gene expression
directly.]

Published in <del>Nature</del> [Genome
Biology](http://genomebiology.com/2013/14/7/R72/abstract)

>

**Background**

Large-scale annotation efforts have improved our ability to coarsely predict
regulatory elements throughout vertebrate genomes. However, it is unclear how
complex spatiotemporal patterns of gene expression driven by these elements
emerge from the activity of short, transcription factor binding sequences.

**Results**

We describe a comprehensive promoter extension assay in which the regulatory
potential of all 6 base-pair (bp) sequences was tested in the context of a
minimal promoter. To enable this large-scale screen, we developed algorithms
that use a reverse-complement aware decomposition of the de Bruijn graph to
design a library of DNA oligomers incorporating every 6-bp sequence exactly
once. Our library multiplexes all 4,096 unique 6-mers into 184 double-stranded
15-bp oligomers, which is sufficiently compact for in vivo testing. We
injected each multiplexed construct into zebrafish embryos and scored GFP
expression in 15 tissues at two developmental time points. Twenty-seven
constructs produced consistent expression patterns, with the majority doing so
in only one tissue. Functional sequences are enriched near biologically
relevant genes, match motifs for developmental transcription factors, and are
required for enhancer activity. By concatenating tissue-specific functional
sequences, we generated completely synthetic enhancers for the notochord,
epidermis, spinal cord, forebrain and otic lateral line, and show that short
regulatory sequences do not always function modularly.

**Conclusions**

This work introduces a unique in vivo catalog of short, functional regulatory
sequences and demonstrates several important principles of regulatory element
organization. Furthermore, we provide resources for designing compact,
reverse-complement aware k-mer libraries.

