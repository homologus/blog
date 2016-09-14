---
title: 2014 - The Year of Minimizers in Bioinformatics
tags: []
categories:
- blog
---
Expensive computer RAM was a major concern for Michael Roberts and colleagues
working on kmer-based bioinformatics algorithms. They wrote -
<!--more-->

> Although currently there exist computers with 20 GB of RAM, they are
expensive.

If you are wondering why they were worrying about only 20GB of RAM, the above
text was written in 2004, when 20GB was indeed quite expensive. Thankfully,
they came up with an elegant solution for storing a subset of kmers called
**'minimizers'** and published in Binformatics.

[Reducing storage requirements for biological sequence comparison](http://bioi
nformatics.oxfordjournals.org/content/20/18/3363.full.pdf+html)

>

Motivation: Comparison of nucleic acid and protein sequences is a fundamental
tool of modern bioinformatics. A dominant method of such string matching is
the seed-and-extend approach, in which occurrences of short subsequences
called seeds are used to search for potentially longer matches in a large
database of sequences. Each such potential match is then checked to see if it
extends beyond the seed. To be effective, the seed-and-extend approach needs
to catalogue seeds from virtually every substring in the database of search
strings. Projects such as mammalian genome assemblies and large-scale protein
matching, however, have such large sequence databases that the resulting list
of seeds cannot be stored in RAM on a single computer. This significantly
slows the matching process.

Results: We present a simple and elegant method in which only a small fraction
of seeds, called minimizers, needs to be stored. Using minimizers can speed up
string-matching computations by a large factor while missing only a small
fraction of the matches found using all seeds.

\----------------------------------------------------------------

The method was mostly forgotten until last year, when a CS-group from Santa
Barbara rediscovered something similar. Since then, minimizers have taken the
bioinformatics world by storm and we suspect this is just the beginning. We
will write about various papers, which all used the concept.

Edit. Hamid Chitsaz and C. Ye pointed out in the comment section that they
both rediscovered the method in 2012 before Li _et al._ did in 2013. We are
changing the order of abstracts to be chronologically correct.

1\. [De novo co-assembly of bacterial genomes from multiple single cells](http
://ieeexplore.ieee.org/xpl/articleDetails.jsp?reload=true&arnumber=6392618)

[Movahedi, N.S.; Forouzmand, E. ; Chitsaz, H.]

> Recent progress in DNA amplification techniques, particularly multiple
displacement amplification (MDA), has made it possible to sequence and
assemble bacterial genomes from a single cell. However, the quality of single
cell genome assembly has not yet reached the quality of normal multiceli
genome assembly due to the coverage bias and errors caused by MDA. Using a
template of more than one cell for MDA or combining separate MDA products has
been shown to improve the result of genome assembly from few single cells, but
providing identical single cells, as a necessary step for these approaches, is
a challenge. As a solution to this problem, we give an algorithm for de novo
co-assembly of bacterial genomes from multiple single cells. Our novel method
not only detects the outlier cells in a pool, it also identifies and
eliminates their genomic sequences from the final assembly. Our proposed co-
assembly algorithm is based on colored de Bruijn graph which has been recently
proposed for de novo structural variation detection. Our results show that de
novo co-assembly of bacterial genomes from multiple single cells outperforms
single cell assembly of each individual one in all standard metrics. Moreover,
co-assembly outperforms mixed assembly in which the input datasets are simply
concatenated. We implemented our algorithm in a software tool called HyDA
which is available from http://compbio.cs.wayne.edu/software/hyda.

2\. [Exploiting sparseness in de novo genome
assembly](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3369186/)

[Ye et al.]

>

Background

The very large memory requirements for the construction of assembly graphs for
de novo genome assembly limit current algorithms to super-computing
environments.

Methods

In this paper, we demonstrate that constructing a sparse assembly graph which
stores only a small fraction of the observed k-mers as nodes and the links
between these nodes allows the de novo assembly of even moderately-sized
genomes (~500 M) on a typical laptop computer.

Results

We implement this sparse graph concept in a proof-of-principle software
package, SparseAssembler, utilizing a new sparse k-mer graph structure evolved
from the de Bruijn graph. We test our SparseAssembler with both simulated and
real data, achieving ~90% memory savings and retaining high assembly accuracy,
without sacrificing speed in comparison to existing de novo assemblers.

The wrote -

> We would like to note that our approach is similar in spirit to the
minimizer idea introduced by Roberts et al. [20]. Their approach is targeted
at the task of detecting k-mers shared between different reads. The
traditional indexing approach requires storing all k-mers within a read.
Roberts et al. [20] propose only storing the lexicographically smallest k-mer
(minimizer) in a size w detection window. They noted that the number of
minimizers is generally smaller than the number of all k-mers (consecutive
k-mers often share a same minimizer), and the memory requirement is further
reduced by storing the smaller-sized minimizers and by using a large detection
window. Our approach for simplifying the de Bruijn graph is similar in spirit
with the minimizer approach, as we only store a sparse sub-sample of the
k-mers found in the reads. Our choice of the k-mers stored in the graph
attempts to approximate a uniform k-mer sampling of the genome, rather than
based on lexicographic ordering. In future research we plan to explore the
relative benefits of the two approaches, by including lexicographic
information within the sparse k-mer selection process.

and

> however we plan to explore in the future the use of the minimizer concept
(described in the Background) to ensure determinism in graph construction.

3\. [Memory Ef?cient Minimum Substring
Partitioning](http://www.cs.ucsb.edu/~xyan/papers/vldb13_debruijn.pdf)

[Li and colleagues]

> Massively parallel DNA sequencing technologies are revolutionizing genomics
research. Billions of short reads generated at low costs can be assembled for
reconstructing the whole genomes. Unfortunately, the large memory footprint of
the existing de novo assembly algorithms makes it challenging to get the
assembly done for higher eukaryotes like mammals. In this work, we investigate
the memory issue of constructing de Bruijn graph, a core task in leading
assembly algorithms, which often consumes several hundreds of gigabytes memory
for large genomes. We propose a disk-based partition method, called Minimum
Substring Partitioning (MSP), to complete the task using less than 10
gigabytes memory, without runtime slowdown. MSP breaks the short reads into
multiple small disjoint partitions so that each partition can be loaded into
memory, processed individually and later merged with others to form a de
Bruijn graph. By leveraging the overlaps among the k-mers (substring of length
k), MSP achieves astonishing compression ratio: The total size of partitions
is reduced from ?(kn) to ?(n), where n is the size of the short read database,
and k is the length of a k-mer. Experimental results show that our method can
build de Bruijn graphs using a commodity computer for any large-volume
sequence dataset.

4\. [MSPKmerCounter: A Fast and Memory Ef?cient Approach for K-mer
Counting](http://cs.ucsb.edu/~yangli/papers/MSPKmerCounter.pdf)

[Li and Yan]

>

Motivation: A major challenge in next-generation genome sequencing (NGS) is to
assemble massive overlapping short reads that are randomly sampled from DNA
fragments. To complete assembling, one needs to finish a fundamental task in
many leading assembly algorithms: counting the number of occurrences of k-mers
(length- k substrings in sequences). The counting results are critical for
many components in assembly (e.g. variants detection and read error
correction). For large genomes, the k-mer counting task can easily consume a
huge amount of memory, making it impossible for large-scale parallel assembly
on commodity servers.

Results: In this paper, we develop MSPKmerCounter, a disk-based approach, to
efficiently perform k-mer counting for large genomes using a small amount of
memory. Our approach is based on a novel technique called Minimum Substring
Partitioning (MSP). MSP breaks short reads into multiple disjoint partitions
such that each partition can be loaded into memory and processed individually.
By leveraging the overlaps among the k-mers derived from the same short read,
MSP can achieve astonishing compression ratio so that the I/O cost can be
significantly reduced. For the task of k-mer counting, MSPKmerCounter offers a
very fast and memory-efficient solution. Experiment results on large real-life
short reads data sets demonstrate that MSPKmerCounter can achieve better
overall performance than state-of-the-art k-mer counting approaches.

Availability: MSPKmerCounter is available at
http://www.cs.ucsb.edu/yangli/MSPKmerCounter

Contact: yangli@cs.ucsb.edu

5\. [On the representation of de Bruijn
graphs](http://arxiv.org/abs/1401.5383)

[Rayan Chikhi and colleagues, also see discussion
[here](http://www.homolog.us/blogs/blog/2014/01/21/de-novo-assembly-human-
genome-1-5-gb-ram/)]

> The de Bruijn graph plays an important role in bioinformatics, especially in
the context of de novo assembly. However, the representation of the de Bruijn
graph in memory is a computational bottleneck for many assemblers. Recent
papers proposed a navigational data structure approach in order to improve
memory usage. We prove several theoretical space lower bounds to show the
limitation of these types of approaches. We further design and implement a
general data structure (DBGFM) and demonstrate its use on a human whole-genome
dataset, achieving space usage of 1.5 GB and a 46% improvement over previous
approaches. As part of DBGFM, we develop the notion of frequency-based
minimizers and show how it can be used to enumerate all maximal simple paths
of the de Bruijn graph using only 43 MB of memory. Finally, we demonstrate
that our approach can be integrated into an existing assembler by modifying
the ABySS software to use DBGFM.

6\. [Kraken: ultrafast metagenomic sequence classification using exact
alignments](http://genomebiology.com/2014/15/3/R46)

[Wood and Salzberg, also see discussion [here](Kraken  Very Good Application
of Jellyfish and Minimizer)]

> Kraken is an ultrafast and highly accurate program for assigning taxonomic
labels to metagenomic DNA sequences. Previous programs designed for this task
have been relatively slow and computationally expensive, forcing researchers
to use faster abundance estimation programs, which only classify small subsets
of metagenomic data. Using exact alignment of k-mers, Kraken achieves
classification accuracy comparable to the fastest BLAST program. In its
fastest mode, Kraken classifies 100 base pair reads at a rate of over 4.1
million reads per minute, 909 times faster than Megablast and 11 times faster
than the abundance estimation program MetaPhlAn. Kraken is available at
http://ccb.jhu.edu/software/kraken/ webcite.

\--------------------------------------------------

What is the minimizer appraoch? It is an efficient way to reduce redundancy
from neighboring kmers, who differ from each other in only one nucleotide
position. The redundancy itself had been noticed by many researchers and a
number of methods ranging from sparse de Bruijn graph to Bloom filters were
used to take it into account.

Minimizer method is similar to building sparse de Bruijn graph, but k-mers are
selected based on a formula. Among a number of neighboring k-mers, the
smallest one is always chosen.

How is 'smallest' defined? Papers 3, 4, 6 used lexicographic order, whereas #5
picked kmers based on their relative frequencies in the read library. We have
not been able to procure enough funds to purchase and read #1 :)

We will come back to this topic, when time permits.

