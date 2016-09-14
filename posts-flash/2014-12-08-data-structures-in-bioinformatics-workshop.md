---
title: Data Structures in Bioinformatics Workshop
tags: []
categories:
- blog
---
Rayan Chikhi posted [web link for a workshop currently taking
place](http://www2.lirmm.fr/~rivals/DSB/) in France and the talks appear quite
fascinating. Even if you cannot attend, you may be able to go through the
papers of the following researchers to see what they are up to.
<!--more-->

> **Simon Puglisi, Univ Helsinki, Finland

Title: Scalable Indexing of Highly Repetitive Data**

Abstract: Advances in DNA sequencing mean databases of thousands of human
genomes will soon be commonplace. This talk will introduce a simple technique
for reducing the size of conventional indexes on such highly repetitive texts.
Given upper bounds on pattern lengths and edit distances, we preprocess the
text with LZ77 to obtain a filtered text, for which we store a conventional
index. Later, given a query, we find all matches in the filtered text, then
use their positions and the structure of the LZ77 parse to find all matches in
the original text. Our experiments show this also significantly reduces query
times.

**Pall Melsted, University of Iceland, Iceland, pmelsted@hi.is 

Title: Bloom filters for fun and profit**

Abstract: A Bloom filter is a simple, fast and memory efficient probabilistic
data structure for storing a set. The Bloom filter has a one sided error, in
the sense that it can give false positive answers to membership, but the error
rate is controlled by the amount of memory used. We will review the use of
Bloom filters in applications such as k-mer counting, assembly and error
correction for HTS datasets. Additionally we will cover some variations of
Bloom filters and introduce a new variant with better memory efficiency for
storing k-mers.

**Guillaume Rizk, INRIA, France, guillaume.rizk@inria.fr 

Title: k-mer counting with minimizers**

Abstract: K-mer counting is a recurrent step in many NGS algorithms (
assembly, read error correction, ). Current approaches are either ram-
intensive (Jellyfish), or disk-based with huge amount of input/output to disk
(DSK, KMC). A new disk-based method based on minimizers introduced by
Deorowicz et al., reduces the amount of I/O by an order of magnitude,
providing both memory frugal and fast k-mer counting. The GATB library (Genome
Assembly & Analysis Tool Box https://gatb.inria.fr) now includes an
implementation of k-mer counting based on those ideas. This talk will detail
the counting procedure, and comparative results.

**Nicola Prezza and Alberto Policriti, Univ. Udine, Italy 

Title: Hashing and indexing with succinct hash data structures**

Abstract: In this talk, we will begin by illustrating how we integrated
hashing and indexing in building an aligner (the ERNE aligner) used to map
short patterns (reads) on a long text (reference) with a limited amount of
errors. Our hash-based strategy builds upon two families of hash functions.
The first, named Hamming-aware, permits to considerably reduce search space by
hashing the entire Hamming ball around the searched pattern to a smaller one.
The second, named de Bruijn, allows to obtain a novel kind of succinct hash
data structure whose space requirements are of n+o(n) bits instead of O(n log
n). We will conclude showing how we obtained new space-time bounds for the
best k-mismatch problem by finding a hash function with both the above
described properties.

**Johannes Kster and Sven Rahmann, Univ. Essen, Germany 

Title: Massively parallel read mapping with the q-group index and PEANUT**

Abstract: We present the q-group index, a novel data structure for read
mapping tailored towards graphics processing units (GPUs) with a small memory
footprint and efficient parallel algorithms for querying and building. On top
of the q-group index we introduce PEANUT, a highly parallel GPU-based read
mapper.

**Bastien Cazaux, Thierry Lecroq and Eric Rivals 

Title: From indexing data structures to de Bruijn graphs**

Abstract: New technologies have tremendously increased sequencing throughput
compared to traditional techniques, thereby complicating DNA assembly. Hence,
assembly programs resort to de Bruijn graphs (dBG) of k-mers of short reads to
compute a set of long contigs, each being a putative segment of the sequenced
molecule. Other types of DNA sequence analysis, as well as preprocessing of
the reads for assembly, use classical data structures to index all substrings
of the reads. It is thus interesting to exhibit algorithms that directly build
a dBG of order k from a pre-existing index, and especially a contracted
version of the dBG, where non branching paths are condensed into single nodes.
Here, we formalise the relationship between suffix trees/arrays and dBGs, and
exhibit linear time algorithms for constructing the full or contracted dBGs.
Finally, we provide hints explaining why this bridge between indexes and dBGs
enables to dynamically update the order k of the graph.

**Gregory Kucherov, Univ. Marne La Valle, France 

Title: Improved filters for the approximate suffix-prefix overlap problem**

Abstract: The approximate suffix-prefix overlap problem is to find all pairs
of strings from a given set such that a prefix of one string is similar to a
suffix of the other. This computation is a basic operation in genome assembly
(overlap-layout-consensus approach) and in read correction (multiple sequence
alignment approach). Valimaki et al. (Information and Computation, 2012) gave
a solution to this problem based on suffix filters. In this work, we propose
two improvements to the method of Valimaki et al. that reduce the running time
of the computation.

This is a joint work with Dekel Tsur (Ben-Gurion University).

**Thierry Lecroq, Univ. Rouen, France 

Title: Fast on-line pattern matching algorithm for highly similar sequences**

Abstract: With the advent of NGS technologies there are more and more genomic
sequences of individuals of the same species available. These sequences only
differ by a very small amount. There is thus a strong need for efficient
algorithms for performing fast pattern matching in such specific sets of
sequences. We will present very efficient algorithms that solves the on-line
exact pattern matching problem in a set of highly similar DNA sequences. The
algorithm we propose extends the Morris-Pratt and Knuth-Morris-Pratt
algorithms and variants of the Boyer-Moore exact string matching algorithm.
Experimental results show that our new algorithms exhibit good performances in
practice.

This is a joint work with N. Ben Nsira and M. Elloumi.

**Solon Pissis, Kings College, London 

Title: Accurate and efficient methods to improve multiple circular sequence
alignment**

Abstract: Multiple sequence alignment is a core computational task in
bioinformatics and has been extensively studied over the past decades. This
computation requires an implicit assumption on the input data: the left- and
right-most position for each sequence is relevant. However, this is not the
case for circular structures; for instance, MtDNA. Efforts have been made to
address this issue but it is far from being solved. We have very recently
introduced a fast algorithm for approximate circular string matching (Barton
et al., Algo Mol Biol, 2014). Here we first show how to extend this algorithm
for approximate circular dictionary matching; and, then, apply this solution
with agglomerative hierarchical clustering to find a sufficiently good
rotation for each sequence. Furthermore, we propose an alternative method that
is suitable for more divergent sequences. We implemented these methods in
BEAR, a programme for improving multiple circular sequence alignment.
Experimental results, using real and synthetic data, show the high accuracy
and efficiency of these new methods in terms of the inferred likelihood-based
phylogenies.

This is a joint work with Carl Barton, Costas S. Iliopoulos, and Fatima
Vayani.

**Djamal Belazzougui, Univ Helsinki, Finland 

Title: BW4SA A sequence analysis library based on the Burrows-Wheeler
transform**

Abstract: Most sequence analysis problems can be solved with the help of the
suffix tree, probably the most important and well-known text indexing data
structure. The main problem with the suffix tree is its excessive space usage.
Given a text T length n over an alphabet of size sigma a suffix tree occupies
O(n log n) bits of space while the text itself occupies only nlog sigma bits
of space. The suffix tree can be used to the sequence analysis problems in O(n
log sigma) time. The compressed suffix tree (Sadakane TOCS 2007) is a
relatively new data structure which uses only O(nlog?) bits of space, and can
simulate any algorithm on the suffix tree at the price of a slowdown by a
factor O((logn)?) for any constant ?>0. Recently, Beller, Berger, Gog,
Ohlenusch and Schnattinger (SPIRE 2011,2012, JDA 2013) presented a general
algorithm based on Burrows-Wheeler transform (BWT) that can be used to find
maximal repeats and solve other sequence analysis problems in O(nlogsigma)
time and bits of space, thus achieving the speed of the suffix tree and the
space-efficiency of the compressed suffix tree. The general idea of the new
algorithm is to enumerate the nodes of the suffix tree by navigating the
suffix link tree (SLT). In a recent paper, Belazzougui, Cunial, Karkkainen and
Makinen (ESA 2013) have shown a different algorithm to traverse the SLT the
O(nlog?) time, given the bidirectional BWT of a sequence and use it to solve
many other sequence analysis problems. In this talk i will present BW4SA
(Burrows-Wheeler for sequence analysis) a sequence analysis library that
implements many of the algorithms presented in (ESA 2013).

This is a joint work in progress with Fabio Cunial. Implementation by Topi
Paavilainen, Paula Lehtola, Max Sandberg, Lassi Vapaakallio, Jarno Alanko and
Ahmed Sobih.

**Alice Heliou, Polytechnique, LIX, Paris 

Title: Linear-time Computation of Minimal Absent Words Using Suffix Array**

Abstract : An absent word of a word y of length n is a word that does not
occur in y. It is a minimal absent word if all its proper factors occur in y.
Minimal absent words have been computed in genomes of organisms from all
domains of life; their computation also provides a fast alternative for
measuring approximation in sequence comparison. In this talk we will present
the first O(n)-time and O(n)-space algorithm for computing all minimal absent
words based on the construction of suffix arrays. Experimental results, using
real and synthetic data, show that our implementation outperforms the existing
one.

This is a joint work with Carl Barton, Laurent Mouchard and Solon Pissis.

**Paola Bonizzoni, Universit Degli Studi di Milano-Bicocca, Italy 

Title: An external memory BWT-based assembler for Next Generation data**

Abstract: The large amount of short read data that are needed for assembling
in some fields (e.g. metagenomic) strongly motivates the investigation of
disk-based approaches to indexing reads. Positive results in this direction
can stimulate the investigation of efficient disk-based algorithms for de novo
assembly of reads. We developed a disk based-algorithm for building string
graphs and we have integrated our implementation into SGA (the most well-known
assembler based string graphs). Besides the integration with an existing
assembler, the main advantages of our algorithm are (1) a main memory
requirement independent of the size of the data set, and (2) a running time
that is competitive with the (memory-based) one of SGA. We have performed an
experimental analysis to determine the current limitations of an external
memory assembler, starting form the state of the art of building an FM-index
and LCP, Suffix Array in external memory.

This is a joint work with Marco Previtali, Universit Degli Studi di Milano-
Bicocca, Italy.

**Guillaume Holley, Univ. Bielefeld, Germany 

Title: Bloom Filter Trie - a data structure for pan-genome storage**

Abstract: High Throughput Sequencing technologies have become fast and cheap
in the past years. As a result, large-scale projects started to sequence tens
to several thousands of genomes per species. The concept of pan-genome has
therefore emerged. It is composed of two parts: The core genome, which
represents the pool of all the genes shared by all the strains of the species,
and the dispensable genome, which represents genes not shared by all strains.
Graphs exhibit good properties for representing a pan-genome, as they avoid
storing redundant information and can represent genomic variants.
Unfortunately, existing tools using this representation are slow or memory
consuming. We present here a new data structure for storing pan-genomes: The
Bloom Filter Trie. This data structure allows to store a pan-genome as an
annotated de-Bruijn graph in a memory efficient way.

This is a joint work with Roland Wittler and Jens Stoye from International
Research Training Group 1906/1 and Genome Informatics, Faculty of Technology,
Bielefeld University, Germany.

**Alexander Schoenhuth, CWI, Amsterdam, Holland 

Title: Genome sequence assembly via maximal clique enumeration**

Abstract: Genomes of unknown ploidy and high diversity, such as those of many
pathogens, can harbor haplotypes of (very) low frequency. While one can
address this by deep sequencing, the elevated error rates that apply for next-
generation sequencing can interfere with the low frequency of the variants
inherent to the low-frequency haplotypes. New ideas for error correction and
haplotype-aware assembly are required when assembling such highly diverse,
polyploid genomes. We present a new method, HaploClique, which is based on
enumerating maximal cliques in overlap-like graphs as an underlying principle.
In these graphs, nodes reflect probability distribution over sequences, which
at the beginning are given by the reads, and edges reflect that two such
distributions are likely to have arisen from the same underlying base
sequence, i.e. from (locally) the same haplotype. Maximal cliques then reflect
maximal ensembles of reads likely to stem from the same haplotype. One then
iterates by transforming max-cliques into nodes and drawing the corresponding
edges among those new nodes, which results in growing, error-corrected
haplotype contigs. As proof of principle, we show that we can reliably
assemble HIV genomes we outperform all prior, state-of-the art methods that
aim at global assembly of highly diverse, polyploid genomes.

This is joint work with Tobias Marschall, MPI Informatics, Saarbruecken, Armin
Toepfer and Niko Beerenwinkel from ETHZ, Basel.

