---
title: Three Helpful Guides for Those Working on Genome Assembly
tags: []
categories:
- blog
---
A. [Rayan Chikhi's slides - comprehensive yet
introductory](http://perso.eleves.bretagne.ens-cachan.fr/~chikhi/2013-evomics-
assembly.pdf)
<!--more-->

Conclusions -

>

What is a good assembly ?

* No total order 

* Main metrics : N50, coverage, accuracy 

* Use QUAST 

How are assemblies made ?

* Typically, using a de Bruijn graph or a string graph. 

* Errors and small variants are removed from the graph. 

* Contigs are just simple paths from the graph. 

Assembly software

* Recommended software for Illumina data : SOAPdenovo2, Allpaths-LG 

* Plethora of other software for custom needs : Minia for low-memory, SGA for 

very accurate assembly, etc..

* Recommended software for 454 data : Newbler, Celera 

A few tips

* How to choose k : always try many values 

* Put the assembler inside a pipeline : error correction, scaffolding, gap-filling 

Case study

* How to assemble a human genome with Minia 

B.

** [New High Throughput Sequencing technologies at the Norwegian Sequencing Centre - and beyond](http://www.slideshare.net/flxlex/new-high-throughput-sequencing-technologies-at-the-norwegian-sequencing-centre-and-beyond) ** from **[Lex Nederbragt](http://www.slideshare.net/flxlex)**

C. [A Good Thread in SeqAnswers
Forum](http://seqanswers.com/forums/showthread.php?p=92907#post92907)

Original question -

> I have some new Illumina data (HiSeq 100b reads- one paired-end (94xe6
reads) and one mate-pair (54xe6 reads) lib.) for a fungal genome (ca. 30MB)
for which a pretty good reference is already assembled/available.

My coverage is about 400X, and I have de novo assembled the new data with both
Velvet (VelvetOptimiser) and Soapdenovo, but based on simple metrics, e.g. #
scaffolds, largest scaffold, N50, this new assembly doesn't appear to be quite
as good as the reference.

I don't have access to the read data used to assemble the original reference,
and I would like see if I can improve it with this additional data. It looks
like you can give Velvet a -long switch for a reference seq, but the
documentation isn't very clear on this. And, I'm not sure how to go about
generating a "new" reference sequence/scaffolds after, for example, using an
aligner, e.g. Bowtie or BWA, to align the new read data to the reference seq.

Can someone suggest/describe the best approach or a pipeline to get where I
want to go with this dataset?

