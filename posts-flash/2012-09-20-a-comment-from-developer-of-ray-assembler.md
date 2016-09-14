---
title: A Comment from Developer of Ray Assembler
tags: []
categories:
- blog
---
Sbastien Boisvert, the developer of Ray assembler, [wrote a long
comment](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-graphs-to-
rectangle-graphs-for-genome-assembly/) that we believe would be helpful for
our readers. So, we are posting it here with slight modifications (=hyperlinks
moved around text):
<!--more-->

>

homolog.us admin: The total length produced by SPAdes is 4927558, but E. coli
K-12 MG1655 has 4.6 Mb. This strongly suggests duplicated genomic regions
caused by misassemblies !

Rick Westerman: You should try [Ray Meta](http://denovoassembler.sf.net) for
your metagenome !

Everyone:

I am the developer and maintainer of the Ray assembler.

Like Rayan Chikki, assemblers is what I do. And like him, I believe that graph
traversal algorithms are better for genome assembly (better than all those
assembly algorithms based on simplification and/or concatenation and/or
erosion).

Anyway, single bacterial genome assembly is pretty much a solved problem if
you want the perfect assembly and if you take the time to look at
[ALLPATHS](http://www.broadinstitute.org/software/allpaths-lg/blog/).

ALLPATHS is probably the best assembler for the correctness of the output, but
its usability and scalability are poor for what I hear (I dont know, I am not
a end user). It produces 1 scaffold, but is not of broad utility because it
needs an huge array of fancy sequencing libraries.

For E. coli with just two insert sizes of 215 +/- 10 and 487 +/- 18 (the
famous SRA001125 benchmark), the Ray assembler generates an assembly in
minutes if you throw 32 Ray processes on the problem on a good interconnect.

The memory usage is below 200 MB per Ray process (virtual memory, this
includes the mapped software library and the Ray executable size too !). So
globally Ray gives the same result produced by these rectangle graphs in
SPAdes, but with less than 6 GB of physical memory and in minutes. And Ray
produces almost no misassemblies, if not 0.

Ray is so easy to use that you wont believe it !!! ;-)

mpiexec -n 32 Ray \

-p \ 

SRR001665_1.fastq \

SRR001665_2.fastq \

-p \ 

SRR001666_1.fastq \

SRR001666_2.fastq \

-o \ 

coli

Output of Ray:

Scaffolds >= 500 nt

Number: 66

Total length: 4583532

Average: 69447

N50: 133425

Median: 41801

Largest: 265822

Our three paradigms for Ray and Ray Meta (and Ray Communities) are:

\- outstanding usability

\- best-in-class correctness

\- infinite scalability

You can actually run Ray on a ultrabook with 8 GB of memory if you dont like
super computers for a bacterial genome. Ultrabooks are quite the things these
days.

The issue with SPAdes and its Paired de Bruijn Graph (PDBG) is combinatorial
explosion. The authors of SPAdes do not seems to see this as a problem though.
In [the paper about
it](http://online.liebertpub.com/doi/abs/10.1089/cmb.2012.0098), no running
times are provided. This fact and the fact provided by Rick Westerman above
about 300 GB for 8 GB of input data strongly indicate that SPAdes is more a
prototype to test theories and models than a software tool ready for the
genomics community.

EULER, also from the group of Pavel Pevzner, was also a prototype with similar
usability features.

All the best !

Sbastien Boisvert

Two comments:

1\. Our blog did not write much on three assemblers - Ray, ABySS and ALLPATHS,
because they were already known to be very good assemblers, when we started
writing, and we never had time to read their papers in detail and present with
some new insight (yes, bad excuse). If you like to explore Ray assembler
further, here are three links you can start with -

[Sourceforge](http://sourceforge.net/projects/denovoassembler/)

[Sebastien's website](http://boisvert.info)

[seqanswers comments on
Ray](http://seqanswers.com/forums/showthread.php?t=4301)

[Ray: simultaneous assembly of reads from a mix of high-throughput sequencing
technologies](http://www.ncbi.nlm.nih.gov/pubmed/20958248)

2\. Regarding SPAdes, we believe its primary appeal is in proposing an
algorithmic approach to use paired end reads within the de Bruijn graph
framework. For that reason, we are not very concerned about the RAM usage and
other performance metrics (except assembly quality) of the assembler. Many
others ([link](http://www.irisa.fr/symbiose/rayan_chikhi),
[link](http://www.homolog.us/blogs/2012/07/30/an-efficient-preprocessing-
module-for-joining-paired-end-reads-before-assembly/)) are also looking into
the same problem and we do not know, whether SPAdes algorithm will be the best
in the long run, but it is unusual enough to start thinking about.

[Rayan ended his thesis slides with](http://www.homolog.us/blogs/2012/08/10
/thesis-slides-from-rayan-chikhi/) \-

**paired short-read assembly will remain a hot topic for at least a few years.**

If he is right, we will have heated arguments for at least a few years :)

