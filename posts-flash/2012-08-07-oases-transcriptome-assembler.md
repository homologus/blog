---
title: Oases Transcriptome Assembler
tags:
- transcriptome assembly
- oases
- velvet
- RNAseq
categories:
- rnaseq
---
We have been using Oases for so long that we failed to report the 'official'
announcement of its arrival.
<!--more-->

[Oases: robust de novo RNA-seq assembly across the dynamic range of expression
levels, Marcel H. Schulz, Daniel R. Zerbino, Martin Vingron and Ewan
Birney.](http://bioinformatics.oxfordjournals.org/content/28/8/1086)

On comparison between Oases, Trinity and transAbyss, a figure from the above
paper has all information you need (_Hint. 'Oases is the best'_)-

![](http://bioinformatics.oxfordjournals.org/content/28/8/1086/F4.medium.gif)

On comparing de novo and reference-based assemblers (i.e. Cufflinks) -

> As could be expected, Cufflinks generally outperforms the de novo assembly
algorithms, as it benefits from using the reference genome to anchor its
assemblies (Fig. 3). Nonetheless, it is interesting to note that as expression
level and therefore coverage depth go up, the gap narrows.

On finding alternatively spliced regions -

> For each assembled transcript, the average number of additionally assembled
transcripts from the same gene are, respectively, 1.21, 1.25, 1.01 and 1.56
for Oases, transABySS, Trinity and Cufflinks. Cufflinks performs better in
that respect, whereas Trinity is less sensitive.

\--------------------

Few personal comments -

1\. We did a run time comparison of Velvet+Oases and Trinity that the readers
[may check](http://www.homolog.us/blogs/2011/08/23/de-novo-transcriptome-
assemblers-%E2%80%93-oases-trinity-etc-%E2%80%93-iii/). We did not compare
outputs.

The readers may also find [this
commentary](http://www.homolog.us/blogs/2012/03/29/can-trinity-be-used-for-
genome-assembly/) helpful in understanding how different programs work.

2\. Two questions may pop up in your mind - (i) Does Oases really give
significantly better transcriptome than Trinity?

(ii) Is there anything in Oases algorithm that allows it to produce better
transcriptome than Trinity?

As per the output presented in above comparative figure, both Velvet and Oases
assembled 822 genes, whereas Trinity identified 180 additional genes and Oases
identified 263 additional genes. So, Oases did not find 180 genes that Trinity
did and Trinity did not find 263 genes that Oases did. Trans-Abyss had another
222 that neither Velvet nor Trinity identified. So, most important conclusion
from the figure is that the set assembled by transAbyss+Oases+Trinity is
significantly bigger than what each program assembled alone.

One thing to note is that Oases paper had the advantage of coming in last and
seeing and improving upon other methods. For example, Trinity has fixed k-mer
size of 25, whereas the Oases trial was run with variable k-mers (19-35nt). We
do not know how much the Trinity results would improve with longer k-mers.

> In these experiments, Oases tends to be more sensitive, Trinity more
accurate. The correlation of small k-mer assemblies and misassembly rates
suggests that homologies between genes are the main source of errors. As reads
get longer, and coverage depths greater, sensitivity will only increase and
users will probably avoid the shorter k-mer lengths for greater accuracy.
Short k-mers will only be necessary to retrieve the very rare transcripts.

