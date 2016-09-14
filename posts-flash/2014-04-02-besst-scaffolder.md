---
title: BESST Scaffolder
tags: []
categories:
- blog
---
Kristoffer (ksahlin) has been working on a couple of scaffolding programs that
our readers will find useful. The first one BESST ([available
here](https://github.com/ksahlin/BESST)) is described as -
<!--more-->

> BESST is a package for scaffolding genomic assemblies. It contains several
modules for e.g. building a "contig graph" from available information,
obtaining scaffolds from this graph, and accurate gap size information (based
on GapEst http://www.ncbi.nlm.nih.gov/pubmed/22923455). For installation, see
docs/INSTALL.txt.

We found the second one even more interesting.
[BESST_RNA](https://github.com/ksahlin/BESST_RNA) scaffolds genomic contigs
based on RNA-seq.

>

Scaffolding of genomic assemblies with RNA seq data.

INPUT:

Required arguments:

-c Path to a contig file. 

-f Path to bamfile of RNA-seq data mapped to assembly. 

-o Path to location for the output. 

Optional arguments

-e The least amount of witness links that is needed to create a link edge in graph (one for each library). 

-T Upper threshold on the distance between RNA reads. RNA reads with distance over this threshold is not considered to be mapped correctly. e.g. could be set to the upper estimated intron size. 

-k Minimum size of contig to be included in the scaffolding. 

-d Check for sequencing duplicates and count only one of them (when computing nr of links) if they are occurring. (default on = 1). 

-z Coverage cutoff for repeat classification > Should be set high (i.e repeat detection turned of) for RNA scaffolding since repeat classification is not trusted with this type of data. [ e.g. -z 1000 says that contigs with coverage over 100 will be discarded from scaffolding.] 

\--mapq Lowest mapping quality allowed in order to use the read. This value is
compared to the mapping quality column in the BAM file. Default = 10.

EXAMPLE RUN:

$ python Main.py 1 -c /path/to/contigfile.fa -f /path/to/bamfile -o
/path/to/output -e 3 -T 20000 -k 500 -d 1 -z 1000

NOTE:

Mapping reads: BESST assumes "PE orientation" the following mapping of RNA
reads:

PE: s t ------> <\-------

Scaffolding is a difficult step for many de Bruijn graph-based assemblers, and
[SSPACE is another standalone
scaffolder](http://www.baseclear.com/landingpages/basetools-a-wide-range-of-
bioinformatics-solutions/sspacev12/) that others like to use. Among
scaffolders incorporated within dBG assembly programs, SPAdes is
algorithmically the most elegant. For a benchmarking of various scaffolders,
please check the following commentary -

[Keith Robisons Perfect Scaffolder Delivered, What
Next?](http://www.homolog.us/blogs/blog/2014/03/06/keith-robisons-perfect-
scaffolder-delivered-next/)

