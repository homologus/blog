---
title: A Few Good Posts on Transcriptome Assembly and Analysis
tags: []
categories:
- rnaseq
---
In the PacBio-related commentary, we wrote -
<!--more-->

> PacBio developed a terrific transcriptome assembler CRAZY. It assembles the
transcripts and isoforms easily and to a high degree of accuracy. Bye bye
Trinity !!

If you are wondering about it, CRAZY is not an acronym. One has to be crazy to
think about assembling transcripts from PacBio reads, given that the reads
themselves are longer than typical genes. You sequence and you get your genes.
No assembly needed.

Researchers are yet to reach that nirvana and the current reality is to do
Illumina sequencing and reconstruct transcriptomes from the short reads. Two
good commentaries are helpful in that respect.

Biocompare blog covers -

[Transcriptome Assembly, No Reference Required!](http://www.biocompare.com
/Editorial-Articles/147637-Transcriptome-Assembly-Now-i-sans-i-Genome/)

> Theres no denying the impact of whole-genome sequencing for basic research
and in the clinic. Reference genomes provide a scaffold upon which to map
traits, trace evolutionary relationships, assess genetic diversity and more,
and for researchers studying well-characterized organisms like Drosophila,
mouse, rat and human, they are invaluable resources.

But for the vast majority of species, whole-genome sequencing is a nonstarter.
Perhaps there are too few investigators interested in the organism to get the
ball rolling. Or maybe its a matter of money. Whatever the reason, despite
deep cost decreases in next-gen sequencing, many researchers simply cannot
justify reading and interpreting every base in their organism of interest.

Fortunately, they dont necessarily have to. A growing number of researchers
are leveraging RNA-seq data to produce a sort of low-rent, partial-genome
assembly, a process called de novo transcriptome assembly. The result doesnt
capture every base, but it does provide information on expressed genes. All it
takes is an RNA-seq dataset, some specialized open-source software tools and
the bioinformatics chops to use them.

Getting Genetics Done has another helpful commentary on Trinity with videos.

[De Novo Transcriptome Assembly with Trinity: Protocol and
Videos](http://gettinggeneticsdone.blogspot.co.uk/2013/10/de-novo-
transcriptome-assembly-trinity.html)

> One of the clearest advantages RNA-seq has over array-based technology for
studying gene expression is not needing a reference genome or a pre-existing
oligo array. De novo transcriptome assembly allows you to study non-model
organisms, cancer cells, or environmental metatranscriptomes. One of the
challenges with de novo transcriptome assembly, above and beyond all the
challenges associated with genome assembly, is the highly varying abundance
(and thus uneven sequencing depth) of different transcripts in a cell.

Several tools have been developed for de novo transcriptome assembly. One of
the most widely used is Trinity, developed at the Broad Institute. Trinity is
free and open-source, and a recent Nature Protocols article walks through
using Trinity for de novo RNA-seq:

Haas, Brian J., et al. "De novo transcript sequence reconstruction from RNA-
seq using the Trinity platform for reference generation and analysis." Nature
protocols 8.8 (2013): 1494-1512.

You can also check our earlier series from two years back -

[De Novo Transcriptome Assemblers Oases, Trinity,
etc.](http://www.homolog.us/blogs/blog/2011/08/15/de-novo-transcriptome-
assemblers-oases-trinity-etc/)

[De Novo Transcriptome Assemblers Oases, Trinity, etc.
II](http://www.homolog.us/blogs/blog/2011/08/22/de-novo-transcriptome-
assemblers-%E2%80%93-oases-trinity-etc-ii/)

[De Novo Transcriptome Assemblers Oases, Trinity, etc.
III](http://www.homolog.us/blogs/blog/2011/08/23/de-novo-transcriptome-
assemblers-%E2%80%93-oases-trinity-etc-%E2%80%93-iii/)

[De Novo Transcriptome Assemblers Oases, Trinity, etc.
IV](http://www.homolog.us/blogs/blog/2011/08/25/de-novo-transcriptome-
assemblers-%E2%80%93-oases-trinity-etc-%E2%80%93-iv/)

[Explaining Output of Trinity Component
Inchworm](http://www.homolog.us/blogs/blog/2011/10/04/explaining-output-of-
trinity-component-inchworm/)

