---
title: Starting to Understand the SPAdes Papers
tags: []
categories:
- blog
---
Last week, we [posted](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-
graphs-to-rectangle-graphs-for-genome-assembly/) an interesting abstract
titled "From de Bruijn Graphs to Rectangle Graphs for Genome Assembly". Thanks
to Aaron Hardin and Nikolay Vyahhi, we received two fascinating papers to read
over the weekend.
<!--more-->

[SPAdes: A New Genome Assembly Algorithm and Its Applications to Single-Cell
Sequencing](http://www.ncbi.nlm.nih.gov/pubmed/22506599)

[From de Bruijn Graphs to Rectangle Graphs for Genome Assembly by Nikolay
Vyahhi, Alex Pyshkin, Son Pham and Pavel A. Pevzner

Their primary objective was to use complete information from paired end (or
mate pair) reads to assemble genomes. Paired end reads are usually treated by
typical de Bruijn assemblers as two separate reads. This morning, [we joked
about smashing LEGO pieces](http://www.homolog.us/blogs/2012/09/16/two-
insignificant/), and you can see that treating two reads from paired end
sequencing as unconnected entities is conceptually equivalent to smashing
LEGOs by hammer (not [Hammer](http://bix.ucsd.edu/projects/hammer/)). The
process leads to loss of valuable information. For example, when each read is
100 nt long, using paired end in the first round of assembly can make read
length go up to 200 or 225 nt. There is world of difference between a genome
covered 50x with 225 nt reads, and genome covered 100x with 100 nt reads. The
difference is even more important in single cell sequencing or
transcriptomics, where the depth of sequencing varies widely between regions.
SPAdes paper was motivated by single cell sequencing.

Paired end information is ignored, because pairing is difficult to handle
under de Bruijn graph formalism due to variable distance between the paired
reads. SPAdes paper deals with that challenge by conceptually treating the
variable distances as error, and adjusting errors as an 'error correction
step', just like most de Bruijn graph-based assembly algorithms run an error-
correction on nucleotides.

SPAdes papers have many innovative ideas, but here are two we have been able
to digest so far -

(i) **Building de Bruijn graph with variable k-mer sizes**: We discussed
earlier that [using small k-mers](http://www.homolog.us/blogs/2012/06/17/an-
intuitive-explanation-for-running-de-bruijn-assembler-with-varying-k-mer-
sizes/) can create dubious paths through de Bruijn graphs, whereas long k-mers
can get the graph fragmented. One common strategy is to use Velvet with
variable k-mer sizes and somehow merge the assemblies, or pick the one with
best N50. Instead SPAdes incorporates variable k-mer size in the de Bruijn
graph itself.

(ii) **k-bimer adjustment and paired assembly graph**: These algorithms are
essentially the core of the paper, and are developed to properly consider
paired end reads. We cannot explain it all today, but we will try to briefly
explain where the rectangles come from. Regular de bruijn graphs for k-mers
can be conceptually seen to form lines or one-dimensional structures,
especially in the regions of the graph without repeats. The rectangles of
SPAdes papers are formed from pairs of such linear simple regions
(mathematically described as h-edge in the paper). Since the lengths of
various non-repetitive regions are different, you get rectangles with two
sides of unequal lengths. The second paper by Nikolay Vyahhi takes that
rectangular graph as a mathematical abstraction, and presents a solution.

We will add more on the above point with few nice pictures, when time permits.

