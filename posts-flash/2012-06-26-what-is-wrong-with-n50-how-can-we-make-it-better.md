---
title: What is Wrong with N50? How can we make it better?
tags:
- N50
categories:
- blog
---
[N50 statistic](http://en.wikipedia.org/wiki/N50_statistic) is widely used by
bioinformaticians to judge the quality of their assemblies, but it is a faulty
measure. Possibly in recognition of that fact, one of the [stated goals of
Assemblathon](http://assemblathon.org/) is to "produce newer metrics for
assessing the quality of a genome assembly that will complement existing
statistics such as N50 contig size". What is wrong with N50 and how can it be
improved?
<!--more-->

Let us first explain, how N50 came to be accepted as a good measure for
comparing assembly qualities. N50 measures the 'average' sizes of long
scaffolds in an assembly by taking into fact that a genome assembly has few
very long scaffolds and many tiny scaffolds. It works well **provided the
genome assembly is mostly error-free.**

[Overlap-layout-consensus assembly
programs](http://www.cbcb.umd.edu/research/assembly_primer.shtml) developed
for Sanger sequences filtered out the repetitive regions, assembled the
remaining reads based on their mutual overlaps, and then linked together the
contigs into longer scaffolds using mate pairs. Although misassemblies were
always present to some extent, having large number of incorrect junctions was
less likely in such a pipeline provided the repetitive regions were filtered
properly.

The de Bruijn graph-based assemblers used for NGS libraries are different,
because the graphs do not exclude k-mers from repetitive regions. In a broad
sense, a de Bruijn graph of a genome has three types of k-mers -

(i) those from the unique regions of the genome and having unique neighbors in
the graph,

(ii) [those from unique regions of genome but having non-unique neighbors in
the graph due to accidental overlaps](http://www.homolog.us/blogs/2012/06/17
/an-intuitive-explanation-for-running-de-bruijn-assembler-with-varying-k-mer-
sizes/),

(iii) those from non-unique or repetitive regions of the genome.

Assembling the first group is easy. The second group was discussed in [this
commentary](http://www.homolog.us/blogs/2012/06/17/an-intuitive-explanation-
for-running-de-bruijn-assembler-with-varying-k-mer-sizes/), and they can be
resolved by additional assembly step such as varying k-mer size or going
through the reads, as Chrysalis step in Trinity does. Resolving the third
group is not easy, and may sometimes be mathematically impossible based on
given data.

The problem with the third group is not that they provide no path of traversal
through the graph, but that they provide too many paths. An aggressive
assembly technique may try to resolve the third group by picking one path out
of many, and thus may get higher N50. However, that N50 is a product of
introducing many incorrect junctions. There is no limit to how many incorrect
junctions can be present in an assembly produced from de Bruijn graph, because
all k-mers from repetitive regions are present in the graph.

What could be a good measure along with N50 to judge the quality of an
assembly? Ideally, it should be the number of erroneous junctions made in the
assembly, but that is impossible to do without knowing what the correct
sequence is, whereas knowledge of the correct sequence is not possible a
priori in an assembly problem.

Here is our proposed solution for a good metric.

Count the k-mer distribution of the assembly and compare it with the k-mer
distribution expected from the reads. Some preliminary thoughts on how it
would work was presented in [this
commentary](http://www.homolog.us/blogs/2011/09/20/maximizing-utility-of-
available-rams-in-k-mer-world/), but let us elaborate further.

Let us say a k-mer 'ATGGGGGGTTAT' appears 20 times in an assembled genome,
whereas it is expected to be an unique k-mer based on k-mer count from the
reads. We can say for sure that the k-mer is wrongly assembled. The same
calculation can be repeated for all k-mers in the assembly, and an aggregate
measure would express how incorrect the placement of various k-mers is.

The above k-mer correctness metric along with N50 can tell us to some extent
whether the high N50 is achieved with mostly correct junctions, or with many
incorrect junctions. We will elaborate on it further in a later commentary.

