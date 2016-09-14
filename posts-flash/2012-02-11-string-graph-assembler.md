---
title: String Graph Assembler
tags: []
categories:
- blog
---
A recent [Genome Research
paper](http://genome.cshlp.org/content/early/2012/01/22/gr.126953.111)
describing an innovative approach for assembling large genomes from NGS data
caught our attention for several reasons. The paper is coauthored by Jared
Simpson, the developer of [ABySS
assembler](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2694472/) and Richard
Durbin, who runs one of the strongest research groups in bioinformatics. Here
we will briefly explain what we like in their approach, and then go over the
details of the algorithm in our following commentaries.
<!--more-->

The most appealing aspect of the Simpson-Durbin algorithm is that it does not
rely on de Bruijn graphs, and instead employs a different graph construction
approach called 'string graph'. String graphs were first proposed by E. W.
Myers in a [2005 publication](http://bioinformatics.oxfordjournals.org/content
/21/suppl_2/ii79.full.pdf+html).

**What is wrong with de Bruijn graph method?**

i) Memory requirement - As you are well aware, construction of de Bruijn
graphs by partitioning all reads into k-mers is memory-intensive. For
mammalian-sized genomes, de Bruijn graph construction from short reads can
take over 1000 GB or more RAM, which is prohibitively expensive.

ii) Loss of information - When we chop reads into k-mers, their connectivity
information is lost. Longer the reads, more information is lost.

Instead of constructing de Bruijn graph, Simpson-Durbin assembler computes
overlaps between all read pairs, and then constructs a string graph based on
the overlaps. Finally, they derive the genome assembly from the string graph.
The memory required by string graph method is considerably lower than de
Bruijn graphs. Thus, this new approach can potentially handle mammalian-sized
genomes at a significantly lower cost. Quoting their latest paper on
comparison of SGA, ABySS, Velvet and SOAPdenovo,

>

Of the four assemblers, SGA used the least memory (4.5 GB vs. 14.1 GB, 23.0 GB
and 38.8 GB for ABySS, Velvet and SOAPdenovo, respectively). The de Bruijn
graph assemblers were considerably more computationally efficient, however, as
the SGA assembly required approximately eight times more CPU hours than ABySS,
20 times more than Velvet, and three times more than SOAPdenovo. This speed
difference is largely due to the time required to build the FM-index. However,
we can reuse one FM-index for multiple runs of SGA, for instance to try
different error correction or assembly parameters, whereas the de Bruijn table
for ABySS, Velvet, and SOAPdenovo must be recalculated for each choice of k.

**Why did nobody else try similar approach before?**

It is because the computation of overlaps between all read pairs is very time-
consuming. The most important innovation of Simpson-Durbin approach comes into
reducing this computational time from quadratic order to linear order of the
number of reads (or rather their sequence length). They achieved it by
representing the reads as suffix array, and then finding the overlaps using
FerraginaManzini index (FM-index) derived from the BurrowsWheeler transform.
The core of Simpson-Durbin algorithm, where they presented the above step, is
[available from an earlier paper](http://bioinformatics.oxfordjournals.org/con
tent/26/12/i367.full#ref-20). In the latest paper, they described use of their
technique on mammalian-sized sequence data.

If you want to learn about String Graph assembler, please read the following
papers -

i) [The Fragment Assembly String Graph - E. W. Myers](http://bioinformatics.ox
fordjournals.org/content/21/suppl_2/ii79.full.pdf+html)

This paper describes the String Graph concept.

ii) [Efficient construction of an assembly string graph using the FM-index -
Jared T. Simpson and Richard Durbin](http://bioinformatics.oxfordjournals.org/
content/26/12/i367.full#ref-20)

This earlier paper from Simpson and Durbin

iii) [Efficient de novo assembly of large genomes using compressed data
structures - Jared T. Simpson and Richard
Durbin](http://genome.cshlp.org/content/early/2012/01/22/gr.126953.111)

