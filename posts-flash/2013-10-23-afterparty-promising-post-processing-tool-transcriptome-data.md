---
title: AfterParty - a Promising Post Processing Tool for Transcriptome Data
tags: []
categories:
- rnaseq
---
A [new paper in BMC
Bioinformatics](http://www.biomedcentral.com/1471-2105/14/301) seems pretty
interesting (h/t: @pathogenomenick). Does it work as advertised?
<!--more-->

Programming language: Groovy (Java)

Project home page: https://github.com/mojones/afterParty2

> Background

Next-generation DNA sequencing technologies have made it possible to generate
transcriptome data for novel organisms quickly and cheaply, to the extent that
the effort required to annotate and publish a new transcriptome is greater
than the effort required to sequence it. Often, following publication, details
of the annotation effort are only available in summary form, hindering
subsequent exploitation of the data. To promote best-practice in annotation
and to ensure that data remain accessible, we have written afterParty, a web
application that allows users to assemble, annotate and publish novel
transcriptomes using only a web browser.

Results

afterParty is a robust web application that implements best-practice
transcriptome assembly, annotation, browsing, searching, and visualization.
Users can turn a collection of reads (from Roche 454 chemistry) or assembled
contigs (from any sequencing chemistry, including Illumina Solexa RNA-Seq)
into a searchable, browsable transcriptome resource and quickly make it
publicly available. Contigs are functionally annotated based on similarity to
known sequences and protein domains. Once assembled and annotated,
transcriptomes derived from multiple species or libraries can be compared and
searched. afterParty datasets can either be created using the existing
afterParty server, or using local instances that can be built easily using a
virtual machine. afterParty includes powerful visualization tools for
transcriptome dataset exploration and uses a flexible annotation architecture
which will allow additional types of annotation to be added in the future.

Conclusions

afterParty's main use case scenario is one in which a working biologist has
generated a large volume of transcribed sequence data and wishes to turn it
into a useful resource that has some durability. By reducing the effort,
bioinformatics skills, and computational resources needed to annotate and
publish a transcriptome, afterParty will facilitate the annotation and sharing
of sequence data that would otherwise remain unavailable. A typical metazoan
transcriptome containing several tens of thousands of contigs can be annotated
in a few minutes of interactive time and a few days of computational time.

