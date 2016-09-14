---
title: Informed and Automated k-Mer Size Selection for Genome Assembly
tags: []
categories:
- blog
---
![genie](http://www.homolog.us/blogs/wp-content/uploads/2013/04/genie.jpg)
<!--more-->

Rayan Chikhi and Paul Medvedev [posted a very good
paper](http://arxiv.org/pdf/1304.5665.pdf) at arxiv.org on optimum k-mer
selection for genome assembly. Like all of Rayan's paper, this one is also
supported by extensive amount of results from real data, insightful comments
and code for others to download and try. The program Kmergenie is available
from [here](http://kmergenie.bx.psu.edu/).

>

We develop a fast and accurate sampling method that constructs approximate
abundance histograms with a several orders of magnitude performance
improvement over traditional methods. We then present a fast heuristic that
uses the generated abundance histograms for putative k values to estimate the
best possible value of k. We test the effectiveness of our tool using diverse
sequencing datasets and ?nd that its choice of k leads to some of the best

assemblies.

The key insight on finding optimal k-mer value is here -

>

Our key insight is that the variation of the estimated numbers of genomic
k-mers present in the reads enables us to determine a suitable k value for
assembly. To see this, consider the number of distinct k-mers in the reference
genome. Observe that as k increases, this number generally increases as a
consequence of repeat instances becoming fully spanned by k-mers. A high
number of distinct genomic k-mer re?ects that more repetitions are resolved.
Hence ideally, if the read coverage was perfect and reads were error-free, the
best value of k for assembly would be the read length. However, in typical
sequencing scenarios, the read coverage is imperfect and reads are error-
prone. Consider obvious high and low thresholds for k: for k close to the read
length, it is unlikely that all the genomic k-mers are in the reads dataset
due to imperfect coverage. For small values of k, any long

enough random string contains almost all possible k-mers ( 4^k). In practice,
this is also true for genomes.

We go further and examine what happens in between these two extreme cases.
Starting from k equal to the read length and progressively decreasing it, two
effects happen simultaneously: (i) the chance that a genomic k-mer appears in
the reads increases, and (ii) the number of distinct k-mers in the reference
genome is likely to decrease, due to repetitions. At the beginning, with large
values of k, the ?rst effect typically dominates the second. Then, decreasing
k, either all the genomic k-mers become present in the reads (andthus a
maximum number of distinct genomic k-mers is reached), or k becomes so low
that nearly all possible k-mers are seen (in that case, the read coverage is
clearly insuf?cient). Assuming the read coverage is high enough to avoid the
latter, decreasing k further only triggers the second effect, and the number
of genomic k-mers strictly decreases.

From these observations, we conclude that the number of genomic k-mers is
likely to reach a maximum value, after which it will steadily decrease. At
this value, all the sequenced genomic k-mers are likely to appear in the
reads, thus the assembly at this k-mer length will be of high coverage. Also,
the assembly is likely to be of high contiguity as a large number of distinct
k-mers imply that more repetitions are fully contained in k-mers.

There is lot more in the paper on genome size estimation, error modeling and
thoughts on how the method is applicable for other types of assembly
algorithms such as SGA.

\----------------

With Rayan's permission, we are sharing parts of a private email exchange, if
that helps in understanding the paper better.

**Homolog.us:** (i) How do you take IDBA into account? 

"More thorough approaches compare assemblies obtained from different k values;
however, they are very time consuming since a single assembly can take days
for mammaliansize genomes"

**Rayan:**

>

IDBA and more recently SOAPdenovo2 indeed are capable of multi-k assembly. As
far as I know, IDBA may not be scalable to large genomes in terms of memory.
And SOAPdenovo2 takes forever to do its multi-k transformations ((largest k -
smallest k) * contig phases, with no way to skip a k-mer size)). We didn't
really discuss these points in the paper: the focus is kept on the large
majority of assemblers which take a single k as

a parameter.

**Homolog.us:** I guess there are two separate issues - algorithm and implementation. In terms of algorithm, IDBA does not have any shortcoming regarding scaling. 

> Yes right, but IDBA does not use a classical single-k de Bruijn graph. So it
is not clear if/how the Minia data structure or the Succinct DBG data
structure could be adapted.

**Homolog.us:** In terms of implementation, only 2-3 assemblers really spent time to have all pieces together into one easy-to-use package. SOAPdenovo2 and ALLPATHS-LG are supposedly the best among them, although I have not tried the second one. Did you get a chance? 

> Yes true. Several collaborators ran AllpathsLG, and I did some test runs. It
was difficult to run some years ago, it got better. It is a really nice
assembler if you have the right type of data.

**Homolog.us:** (ii) Have you checked the method for transcriptome and metagenomes, or is it valid for large single genomes only? 

**Rayan:**

> Havn't checked for transcriptomes or metagenomes, but I suspect it won't
work as is (first paragraph in the discussion). For
transcriptomes/metagenomes, I suspect that multi-k approaches like IDBA are
the way to go. But kmergenie could nevertheless provide some information on
the expected size of assembly for a fixed k (Trinity comes to mind).

