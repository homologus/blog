---
title: A Must Read Book, If You Like to Understand Genomes
tags: []
categories:
- sponsored
---
Over the last two weeks, I have been reading a fascinating book that came out
recently and would like to strongly recommend it to our readers. This book,
written by [Caltech professor Eric
Davidson](http://www.its.caltech.edu/~davidson/) and his former student
Isabelle Peter, is one of those rare gems that will continue to influence
researchers many decades from today.
<!--more-->

![Genomic-Control-Process-210x271](http://www.homolog.us/blogs/wp-
content/uploads/2015/05/Genomic-Control-Process-210x271.jpg)

With the cost of nucleotide sequencing going down, it is now possible to
sequence the genomes of many interesting organisms. The first few steps of the
genome projects, namely sequencing, assembly and gene annotation, have become
fairly straightforward, but how to connect the genome and genes with the
biological novelties of the organisms is not at all clear. Davidson and
Peter's book presents a systematic way to make sense of the genomes based on
their work on sea urchin over the last fifteen years.

![davidson-copy](http://www.homolog.us/blogs/wp-content/uploads/2015/05
/davidson-copy-197x300.jpg)

For those who do not know, [Eric
Davidson](http://www.its.caltech.edu/~davidson/) used to be the keynote
speaker at almost all bioinformatics conferences in early 2000s. The draft
human and mouse genomes just got published at that time, and many scientists
were looking for ways to connect the genome with complex body plan. Eric
Davidson, a developmental biologist, described a way to do so, and many
researchers found his ideas thought-provoking. His method on gene regulatory
network combined experiments and computation with the computational aspects
being developed in close collaboration with Hamid Bolouri, an electrical
engineer. Bolouri was at Caltech at that time, but later moved to Institute of
Systems Biology, Seattle and then Fred Hutch Cancer Research Center.

The fact that Davidson and his collaborators really understood how to make
sense of the genome became clear to me, when I worked closely with them in
mid-2000 as part of the sea urchin genome project. At that time, I worked with
a number of other genome projects, but the sea urchin one stood out as
unusual. The community knew exactly why they needed the genome, and even
before the genome was properly assembled, they were ready with annotating all
transcription factors and measuring their expression profile during early
development. The community manually annotated over 10,000 genes and it was
quite a remarkable experience working with such a vibrant group of scientists.

Equally remarkable was what Davidson and his collaborators achieved since
then. In 2012, Peter, Faure and Davidson published a PNAS paper titled -

["Predictive computation of genomic logic processing functions in embryonic
development"](http://www.pnas.org/content/109/41/16434.abstract), where they
presented a predictive Boolean model to describe each step of the early
development process up to gastrulation. Nothing like this has been done in any
other organism.

> Gene regulatory networks (GRNs) control the dynamic spatial patterns of
regulatory gene expression in development. Thus, in principle, GRN models may
provide system-level, causal explanations of developmental process. To test
this assertion, we have transformed a relatively well-established GRN model
into a predictive, dynamic Boolean computational model. This Boolean model
computes spatial and temporal gene expression according to the regulatory
logic and gene interactions specified in a GRN model for embryonic development
in the sea urchin. Additional information input into the model included the
progressive embryonic geometry and gene expression kinetics. The resulting
model predicted gene expression patterns for a large number of individual
regulatory genes each hour up to gastrulation (30 h) in four different spatial
domains of the embryo. Direct comparison with experimental observations showed
that the model predictively computed these patterns with remarkable spatial
and temporal accuracy. In addition, we used this model to carry out in silico
perturbations of regulatory functions and of embryonic spatial organization.
The model computationally reproduced the altered developmental functions
observed experimentally. Two major conclusions are that the starting GRN model
contains sufficiently complete regulatory information to permit explanation of
a complex developmental process of gene expression solely in terms of genomic
regulatory code, and that the Boolean model provides a tool with which to test
in silico regulatory circuitry and developmental perturbations.

I came to further grasp the tremendous significance of Davidson's work, when I
was looking for ideas to make sense of the [electric eel
genome](http://www.ncbi.nlm.nih.gov/pubmed/24970089). The electric organs
evolved six times independently in various fish species, but how can one go
from the genome or annoated genes to say something biologically meaningful? At
first, we were trying all kinds of popular bioinformatics methods (sequence
conservation, phylogeny, accelerated evolution), but came to realize that
Davidson's approach was the only way to go. So, we decided to get gene
expression profiles (RNAseq) in muscle and electric organ in multiple electric
fish independently evolving electric organs and compared data to identify
relevant genes. Although our work is far short of what the sea urchin
community has done, it is a step in right direction.

After the electric fish experience, I decided to get both of his earlier books
(["Genomic Regulatory System"](http://www.amazon.com/Genomic-Regulatory-
Systems-Development-Evolution/dp/0122053516/ref=asap_bc?ie=UTF8) and ["The
Regulatory Genome"](http://www.amazon.com/Regulatory-Genome-Networks-
Development-Evolution/dp/0120885638/ref=asap_bc?ie=UTF8)) and read them
completely. The latest book presents many of the concepts in simple language,
and I recommend it to every bioinformatics researcher so that they have good
understanding of the big picture.

We convinced the publisher (Elsevier) to share a chapter with our readers
(click [here](http://www.homolog.us/blogs/wp-
content/uploads/2015/05/e9780124047297_Chapter2.pdf) to read, if embed does
not work). Also, if you are [purchasing at the Elsevier website](http://store.
elsevier.com/product.jsp?isbn=9780124047464&_requestid=1619404) by going from
our blog, please use the code BIOMED315 to get a 30% discount on the price.

<div id="report"></div>
<script src="/assets/js/pdfobject.js"></script>
<script>PDFObject.embed("http://www.homolog.us/blogs/wp-content/uploads/2015/05/e9780124047297_Chapter2.pdf", "#report");</script>
