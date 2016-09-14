---
title: ASHG&#47;GA4GH Special - A Recap of Interesting NGS Algorithms of the Year
tags: []
categories:
- blog
---
If you find our commentaries useful, please feel free to press the donate
button on the right sidebar and your name will be included in the table at the
bottom of the page. We thank Pawel Osipowski, a PhD student from Poland, for
making today's generous contribution to support our blog.
<!--more-->

![images](http://www.homolog.us/blogs/wp-content/uploads/2014/10/images.jpg)

Section 1 covers algorithms for short reads (primarily Illumina). The reads
are clean and the main problem is the volume of data. The size of each library
can be 50-100G and imagine doing that for 10,000 human genomes together. The
tags: []
categories for challenging problems are - base-calling, kmer counting (the
most basic step), de Bruijn graph construction, genome assembly, BWT
construction of large library, compression of large libraries, searching
through many such genomes and expression analysis.

Section 2 covers long noisy reads primarily from PacBio, but should also be
equally applicable for nanopore data. The challenge here is how to take care
of the noise in the reads.

Section 3 covers GPU acceleration, which is one of the ways to go over the
data analysis bottleneck.

Section 4 asks the question of whether it is really necessary to keep scaling
up from 10K genomes to 100K genomes and so on, or can we answer biological
questions by trying a different route.

Section 5 mentions two new blogs started this year by skilled
bioinformaticians.

Section 6 adds a number of interesting papers missed in the first cut. We went
through all issues of arxiv/biorxiv and tried to find every interesting paper.

Enjoy and feel free to comment, distribute, criticize, flame us or whatever !!

\------------------------------------------------------------

\------------------------------------------------------------

**1\. Algorithms for Short Reads**

**KMC - Minimizer-based Kmer Counting Algorithm for Short Reads**

[KMC 2: Fast and resource-frugal k-mer
counting](http://www.homolog.us/blogs/blog/category/genome-assembly-2/k-mer-
counting-genome-assembly-2/)

> Motivation: Building the histogram of occurrences of every k-symbol long
substring of nucleotide data is a standard step in many bioinformatics
applications, known under the name of k-mer counting. Its applications include
developing de Bruijn graph genome assemblers, fast multiple sequence alignment
and repeat detection. The tremendous amounts of NGS data require fast
algorithms for k-mer counting, preferably using moderate amounts of memory.

Results: We present a novel method for k-mer counting, on large datasets at
least twice faster than the strongest competitors (Jellyfish~2, KMC~1), using
about 12\,GB (or less) of RAM memory. Our disk-based method bears some
resemblance to MSPKmerCounter, yet replacing the original minimizers with
signatures (a carefully selected subset of all minimizers) and using
(k,x)-mers allows to significantly reduce the I/O, and a highly parallel
overall architecture allows to achieve unprecedented processing speeds. For
example, KMC~2 allows to count the 28-mers of a human reads collection with
44-fold coverage (106\,GB of compressed size) in about 20 minutes, on a 6-core
Intel i7 PC with an SSD.

We also discussed another efficient kmer counting program -
[scTurtle](http://www.homolog.us/blogs/blog/2014/04/09/scturtle-algorithm-for-
kmer-counting/) \- in our blog.

\------------------------------------------------------------

**BCALM - Chikhi et al.'s Algorithm for dBG Construction using Minimizer**

[De Novo Assembly of Human Genome with Only 1.5 GB
RAM](http://www.homolog.us/blogs/blog/2014/01/21/de-novo-assembly-human-
genome-1-5-gb-ram/)

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

\------------------------------------------------------------

**Kraken - Minimizer-based Algorithm for Metagenome Classification**

[Kraken: Ultrafast Metagenomic Sequence Classification Using Exact
Alignments](http://www.homolog.us/blogs/blog/2014/03/07/kraken-good-
application-jellyfish-minimizer/)

> Kraken is an ultrafast and highly accurate program for assigning taxonomic
labels to metagenomic DNA sequences. Previous programs designed for this task
have been relatively slow and computationally expensive, forcing researchers
to use faster abundance estimation programs, which only classify small subsets
of metagenomic data. Using exact alignment of k-mers, Kraken achieves
classification accuracy comparable to the fastest BLAST program. In its
fastest mode, Kraken classifies 100 base pair reads at a rate of over 4.1
million reads per minute, 909 times faster than Megablast and 11 times faster
than the abundance estimation program MetaPhlAn. Kraken is available at
http://ccb.jhu.edu/software/kraken/.

\------------------------------------------------------------

**BWT Construction for Large Short-read Library**

Heng Li's ropebwt2 paper.

[Fast construction of FM-index for long sequence
reads](http://www.homolog.us/blogs/blog/2014/06/12/fast-construction-of-fm-
index-for-long-sequence-reads/)

> We mentioned Heng Lis ropebwt2 code at github in the past, but now he
discloses the algorithm in a brief paper posted at arxiv. We will spend the
rest of the day trying to understand what is going on.

Summary: We present a new method to incrementally construct the FM-index for
both short and long sequence reads, up to the size of a genome. It is the
first algorithm that can build the index while implicitly sorting the
sequences in the reverse (complement) lexicographical order without a separate
sorting step. The implementation is among the fastest for indexing short reads
and the only one that practically works for reads of averaged kilobases in
length. Availability and implementation: https://github.com/lh3/ropebwt2
Contact: hengli@broadinstitute.org

Is constructing FM index still relevant in the Minimizer world?

Rayan Chikhi worked through an example here that you will find helpful.

Also check -

[BWT Construction Parallelized in
Parabwt](http://www.homolog.us/blogs/blog/2014/08/15/bwt-construction-
parallelized-in-parabwt/)

[BEETL-fastq: a searchable compressed archive for DNA
reads](http://arxiv.org/abs/1406.4376)

FASTQ is a standard file format for DNA sequencing data which stores both
nucleotides and quality scores. A typical sequencing study can easily generate
hundreds of gigabytes of FASTQ files, while public archives such as ENA and
NCBI and large international collaborations such as the Cancer Genome Atlas
can accumulate many terabytes of data in this format. Text compression tools
such as gzip are often employed to reduce the storage burden, but have the
disadvantage that the data must be decompressed before it can be used.

> Here we present BEETL-fastq, a tool that not only compresses FASTQ-formatted
DNA reads more compactly than gzip, but also permits rapid search for k-mer
queries within the archived sequences. Importantly, the full FASTQ record of
each matching read or read pair is returned, allowing the search results to be
piped directly to any of the many standard tools that accept FASTQ data as
input.

Results:

We show that 6.6 terabytes of human reads in FASTQ format can be transformed
into 1.7 terabytes of indexed files, from where we can search for 1, 10, 100,
1000, a million of 30-mers in respectively 3, 8, 14, 45 and 567 seconds plus
20 ms per output read. Useful applications of the search capability are
highlighted, including the genotyping of structural variant breakpoints and
"in silico pull-down" experiments in which only the reads that cover a region
of interest are selectively extracted for the purposes of variant calling or
visualization.

Availability:

BEETL-fastq is part of the BEETL library, available as a github repository at
git@github.com:BEETL/BEETL.git.

\------------------------------------------------------------

**Compression of Large Libraries**

[BARCODE - Fast lossless compression via cascading Bloom
filters](http://www.homolog.us/blogs/blog/2014/05/08/barcode-fast-lossless-
compression-via-cascading-bloom-filters/)

[BMC Bioinformatics paper](http://www.biomedcentral.com/1471-2105/15/S9/S7) \-

>

Background

Data from large Next Generation Sequencing (NGS) experiments present
challenges both in terms of costs associated with storage and in time required
for file transfer. It is sometimes possible to store only a summary relevant
to particular applications, but generally it is desirable to keep all
information needed to revisit experimental results in the future. Thus, the
need for efficient lossless compression methods for NGS reads arises. It has
been shown that NGS-specific compression schemes can improve results over
generic compression methods, such as the Lempel-Ziv algorithm, Burrows-Wheeler
transform, or Arithmetic Coding. When a reference genome is available,
effective compression can be achieved by first aligning the reads to the
reference genome, and then encoding each read using the alignment position
combined with the differences in the read relative to the reference. These
reference-based methods have been shown to compress better than reference-free
schemes, but the alignment step they require demands several hours of CPU time
on a typical dataset, whereas reference-free methods can usually compress in
minutes.

Results

We present a new approach that achieves highly efficient compression by using
a reference genome, but completely circumvents the need for alignment,
affording a great reduction in the time needed to compress. In contrast to
reference-based methods that first align reads to the genome, we hash all
reads into Bloom filters to encode, and decode by querying the same Bloom
filters using read-length subsequences of the reference genome. Further
compression is achieved by using a cascade of such filters.

Conclusions

Our method, called BARCODE, runs an order of magnitude faster than reference-
based methods, while compressing an order of magnitude better than reference-
free methods, over a broad range of sequencing coverage. In high coverage
(50-100 fold), compared to the best tested

compressors, BARCODE saves 80-90% of the running time while only increasing
space slightly.

[Minimizer Success Disk-based Genome Sequencing Data
Compression](http://www.homolog.us/blogs/blog/2014/05/28/minimizer-success-
disk-based-genome-sequencing-data-compression/)

> We propose ORCOM (Overlapping Reads COmpression with Minimizers), a
compression algorithm dedicated to sequencing reads (DNA only). Most
compressors for such data, usually in FASTQ format, cannot efficiently
compress the DNA stream if a given dataset is large, since the redundancy
between overlapping reads cannot be easily exploited in the main memory, often
a few times smaller than the amount of data to compress. More interesting
solutions for this problem are disk-based~\cite{Y2011,CBJR2012}, where the
better of these two, from Cox~et al.~\cite{CBJR2012}, is based on the
BurrowsWheeler transform (BWT) and achieves 0.484\,bits per base for a
135.3\,Gbp human genome sequencing collection with 45-fold coverage. Our
method makes use of a conceptually simple and easily parallelizable idea of
minimizers, to obtain 0.376\,bits per base as the compression ratio.

\------------------------------------------------------------

**Searching from Many Genomes**

Check [this development from David Haussler's
group](http://www.homolog.us/blogs/blog/2014/04/23/mapping-to-a-graph-style-
reference-genome-arxiv-paper/).

> David Haussler and colleagues had been working on how to align a new read
library against thousands of human genomes. The easy solution of performing
the same alignment thousand times does not scale well. Benedict Paten, Adam
Novak and David Haussler posted a new paper in arxiv to address this question.
This appears like an interesting paper, but we have not read it carefully to
understand the innovation beyond what Juni Siren (corrected) and others
proposed before.

To support comparative genomics, population genetics, and medical genetics, we
propose that a reference genome should come with a scheme for mapping each
base in any DNA string to a position in that reference genome. We refer to a
collection of one or more reference genomes and a scheme for mapping to their
positions as a reference structure. Here we describe the desirable properties
of reference structures and give examples. To account for natural genetic
variation, we consider the more general case in which a reference genome is
represented by a graph rather than a set of phased chromosomes; the latter is
treated as a special case.

Readers may also find the following work from Haussler group relevant

HAL: a Hierarchical Format for Storing and Analyzing Multiple Genome
Alignments

\------------------------------------------------------------

**SPAdes for Genome Assembly**

When it comes to genome assembly, SPAdes group stands way apart from others by
publishing many new developments every year.

[SPAdes Groups Long-awaited Repeat Resolver Paper is
Published](http://www.homolog.us/blogs/blog/2014/06/23/spades-groups-long-
awaited-repeat-resolver-paper-is-published/)

[dipSpades Beats Haplomerger Hands Down in Diploid
Assembly](http://www.homolog.us/blogs/blog/2014/03/04/dipspades-beats-
haplomerger-hands-diploid-assembly/)

Also, Pavel Pevzner, who leads this group, published an interesting paper on
manifold de Bruijn graph. We are not sure whether it is incorporated in SPAdes
yet.

[Manifold de Bruijn Graphs - Yu Lin and Pavel A.
Pevzner](http://www.homolog.us/blogs/blog/2014/09/08/wabistan-report/)

> Genome assembly is usually abstracted as the problem of reconstructing a
string from a set of its k-mers. This abstraction naturally leads to the
classical de Bruijn graph approachthe key algorithmic technique in genome
assembly. While each vertex in this approach is labeled by a string of the
fixed length k, the recent genome assembly studies suggest that it would be
useful to generalize the notion of the de Bruijn graph to the case when
vertices are labeled by strings of variable lengths. Ideally, we would like to
choose larger values of k in high-coverage regions to reduce repeat collapsing
and smaller values of k in the low-coverage regions to avoid fragmentation of
the de Bruijn graph. To address this challenge, the iterative de Bruijn graph
assembly (IDBA) approach allows one to increase k at each iterations of the
graph construction. We introduce the Manifold de Bruijn (M-Bruijn) graph (that
generalizes the concept of the de Bruijn graph) and show that it can provide
benefits similar to the IDBA approach in a single iteration that considers the
entire range of possible k-mer sizes rather than varies k from one iteration
to another.

\------------------------------------------------------------

**BESST for Scaffolding During Genome Assembly**

[Link](http://www.homolog.us/blogs/blog/2014/04/02/besst-scaffolder/)

> BESST is a package for scaffolding genomic assemblies. It contains several
modules for e.g. building a contig graph from available information, obtaining
scaffolds from this graph, and accurate gap size information (based on GapEst
http://www.ncbi.nlm.nih.gov/pubmed/22923455). For installation, see
docs/INSTALL.txt.

\------------------------------------------------------------

**Sailfish for RNAseq Expression Analysis**

For RNAseq expression profiling, Sailfish reduced the time of analysis by
doing it straight from kmers instead of reads.

Check -

[Goodbye RSEM, Sailfish Paper
Published](http://www.homolog.us/blogs/rnaseq/2014/04/21/goodbye-rsem-
sailfish-paper-published/)

> We wrote about very fast Sailfish algorithm, when it came out in the arxiv
(DEseq and Sailfish Papers for RNAseq). Also, one of our readers liked the
code and we wrote about it as well

Good C++ Development Practices in Sailfish Code

Now the readers can find the published paper in Nature Biotech. There is no
excuse for not using it.

\------------------------------------------------------------

**Blindcall for Base-calling**

[BlindCall: Ultra-fast Base-calling Algorithm Using Blind
Deconvolution](http://www.homolog.us/blogs/blog/2014/01/23/blindcall-ultra-
fast-base-calling-algorithm-using-blind-deconvolution/)

> Motivation: Base-calling of sequencing data produced by highthroughput

sequencing platforms is a fundamental process in current bioinformatics
analysis. However, existing third-party probabilistic or machine-learning
methods that significantly improve the accuracy of base-calls on these
platforms are impractical for production use due to their computational
inefficiency.

Results: We directly formulate base-calling as a blind deconvolution problem
and implemented BlindCall as an efficient solver to this inverse problem.
BlindCall produced base-calls at accuracy comparable to state-of-the-art
probabilistic methods while processing data at rates ten times faster in most
cases. The computational complexity of BlindCall scales linearly with read
length making it better suited for new long-read sequencing technologies.

Availability and Implementation: BlindCall is implemented as a set of Matlab
scripts available for download at http://cbcb.umd.edu/~hcorrada/secgen.

\-------------------------------------------------------------

\-------------------------------------------------------------

**2\. Pacbio Reads**

**DALIGN - Pacbio Aligner**

[In DALIGN Paper, Gene Myers Delivers a Major Blow to His Biggest
Competitor](http://www.homolog.us/blogs/blog/2014/07/28/in-dalign-paper-gene-
myers-delivers-a-major-blow-to-his-biggest-competitor/)

It is a very neat paper, because Gene Myers showed here a way to speed up
alignment algorithms without going through BWT construction. It stands out of
the norm from most other NGS alignment algorithms.

**MHAP - Adam Philippy**

[After HGAP And SPAdes Comes New PacBio Assembler
MHAP](http://www.homolog.us/blogs/blog/2014/08/15/after-hgap-and-spades-comes-
new-pacbio-assembler-mhap/)

**Hybrid Assembly**

[Very Efficient Hybrid Assembler for PacBio
Data](http://www.homolog.us/blogs/blog/2014/10/13/very-efficient-hybrid-
assembler-for-pacbio-data/)

> Reader Chengxi Ye mentioned to us a few months back that he developed a very
efficient genome assembler for PacBio data, which did PacBio assembly of human
genome in 6 hours on a desktop computer compared to >400K CPU hours using a
cluster. For those, who do not know Chengxi Ye, he was the author of
SparseAssembler and also developed ultrafast basecaller BlindCall. The
algorithm of SparseAssembler is more relevant in the current context, because
he leveraged its compression scheme in the new PacBio/hybrid assembler.

\-------------------------------------------------------------

\-------------------------------------------------------------

**3\. Hardware Acceleration - GPU**

This year, Professor T.-W. Lam's group at HKU published a number of papers on
hardware acceleration of bioinformatics algorithms using GPU. Although they
are mostly for short reads, we make a separate category here.

[BWT Construction using GPU](http://www.homolog.us/blogs/blog/2014/01/29/gpu-
accelerated-bwt-construction-large-collection-short-reads/)

> This new preprint from Chi-Man Liu, Ruibang Luo and Tak-Wah Lam is worth
checking out (h/t: @lexnederbragt) !! BWT construction is a major problem for
large NGS read files, and as we discussed in What Problems are Being Solved by
the Top NGS Bioinformaticians Today?, almost every top bioinformatician has a
BWT-construction project going on. There are several benefits of turning read
files into BWT quickly.

(i) faster compression and easy transfer (Tony Coxs rearranging of reads is a
good example),

(ii) quick search through a large set of reads,

(iii) k-mer counting is an equivalent problem as BWT construction (see BWT
Construction and K-mer Counting),

(iv) genome assembly using SGA-type of algorithm.

[BALSA for Variant Calling using
GPU](http://www.homolog.us/blogs/blog/2014/04/24/balsa-integrated-secondary-
analysis-for-whole-genome-and-whole-exome-sequencing-accelerated-by-gpu/)

> This paper reports an integrated solution, called BALSA, for the secondary
analysis of next generation sequencing data; it exploits the computational
power of GPU and an intricate memory management to give a fast and accurate
analysis. From raw reads to variants (including SNPs and Indels), BALSA, using
just a single computing node with a commodity GPU board, takes 5.5 hours to
process 50-fold whole genome sequencing (~750 million 100bp paired-end reads),
or just 25 minutes for 210-fold whole exome sequencing. BALSAs speed is rooted
at its parallel algorithms to effectively exploit a GPU to speed up processes
like alignment, realignment and statistical testing. BALSA incorporates a
16-genotype model to support the calling of SNPs and Indels and achieves
competitive variant calling accuracy and sensitivity when compared to the
ensemble of six popular variant callers. BALSA also supports efficient
identification of somatic SNVs and CNVs; experiments showed that BALSA
recovers all the previously validated somatic SNVs and CNVs, and it is more
sensitive for somatic Indel detection. BALSA outputs variants in VCF format. A
pileup-like SNAPSHOT format, while maintaining the same fidelity as BAM in
variant calling, enables efficient storage and indexing, and facilitates the
App development of downstream analyses.

[MEGAHIT - Metagenome Assembly using
GPU](http://www.homolog.us/blogs/blog/2014/09/25/megahit-an-ultra-fast-single-
node-solution-for-large-and-complex-metagenomics-assembly-via-succinct-de-
bruijn-graph/)

> MEGAHIT is a NGS de novo assembler for assembling large and complex
metagenomics data in a time- and cost-efficient manner. It finished assembling
a soil metagenomics dataset with 252Gbps in 44.1 hours and 99.6 hours on a
single computing node with and without a GPU, respectively. MEGAHIT assembles
the data as a whole, i.e., it avoids pre-processing like partitioning and
normalization, which might compromise on result integrity. MEGAHIT generates 3
times larger assembly, with longer contig N50 and average contig length than
the previous assembly. 55.8% of the reads were aligned to the assembly, which
is 4 times higher than the previous. The source code of MEGAHIT is freely
available at this https URL under GPLv3 license.

\--------------------------------------------------------------

\-------------------------------------------------------------

**4\. Future**

What should one do with so many efficient algorithms? The conventional answer
is to cure human diseases, but we believe the companies are over-investing in
this space. Our proposal is presented in the following commentaries.

[Bioinformatics at a Crossroad Again Which Way
Next?](http://www.homolog.us/blogs/blog/2014/08/11/bioinformatics-at-a
-crossroad-again-which-way-next/)

[Crossroads (ii) Is It Too Late to Acknowledge that Systems Biology and GWAS
Failed?](http://www.homolog.us/blogs/blog/2014/09/02/crossroads-ii-is-it-too-
late-to-acknowledge-that-systems-biology-and-gwas-failed/)

[Crossroads (iii) a New Direction for Bioinformatics with Twelve Fundamental
Problems](http://www.homolog.us/blogs/blog/2014/10/14/crossroads-iii-a-new-
direction-for-bioinformatics-with-twelve-fundamental-problems/)

To spare you from reading three long posts, here is a summary. We believe the
new algorithms will be useful in solving fundamental problems in biology, and
that process will eventually lead to curing health or other practical
problems. The current attempts are too superficial.

To solve fundamental problems, the biologists and computer scientists need to
meet halfway and learn quite a bit about each other's field. That is the
direction in which we like to take our blog from next year. All other
suggestions are welcome.

\--------------------------------------------------------------

\-------------------------------------------------------------

**5\. New blogs**

A number of new bioinformatics blogs came online in 2014. Here are a few
noteworthy ones.

[Gene Myers' Dazzler Blog](http://dazzlerblog.wordpress.com/)

[James Knight's Blog at Yale](http://knightlab.commons.yale.edu/gava-pt-1/)

If you think we missed any noteworthy contribution (including yours), please
feel free to mention in the comment section.

\----------------------------------------------------------------------------

Edit. **6\. New Additions**

After completing this commentary, we went to biorxiv to see whether we missed
any other interesting development. The following papers appear noteworthy. We
cannot guarantee that all of them are excellent, and welcome readers' comment
to spare us from reading so many papers.

[Lighter: fast and memory-efficient error correction without
counting](http://www.homolog.us/blogs/blog/2014/05/28/lighter-fast-and-memory-
efficient-error-correction-without-counting/)

It is from the same group that developed Jellyfish and Sailfish.

> Lighter is a fast, memory-efficient tool for correcting sequencing errors.
Lighter avoids counting k-mers. Instead, it uses a pair of Bloom filters, one
holding a sample of the input k-mers and the other holding k-mers likely to be
correct. As long as the sampling fraction is adjusted in inverse proportion to
the depth of sequencing, Bloom filter size can be held constant while
maintaining near-constant accuracy. Lighter is parallelized, uses no secondary
storage, and is both faster and more memory-efficient than competing
approaches while achieving comparable accuracy.

[Compression of short-read sequences using path
encoding](http://biorxiv.org/content/early/2014/06/24/006551)

Another one from the same group.

> Storing, transmitting, and archiving the amount of data produced by next
generation sequencing is becoming a significant computational burden. For
example, large-scale RNA-seq meta-analyses may now routinely process tens of
terabytes of sequence. We present here an approach to biological sequence
compression that reduces the difficulty associated with managing the data
produced by large-scale transcriptome sequencing. Our approach offers a new
direction by sitting between pure reference-based compression and reference-
free compression and combines much of the benefit of reference-based
approaches with the flexibility of de novo encoding. Our method, called path
encoding, draws a connection between storing paths in de Bruijn graphs --- a
common task in genome assembly --- and context-dependent arithmetic coding.
Supporting this method is a system, called a bit tree, to compactly store sets
of kmers that is of independent interest. Using these techniques, we are able
to encode RNA-seq reads using 3% -- 11% of the space of the sequence in raw
FASTA files, which is on average more than 34% smaller than recent competing
approaches. We also show that even if the reference is very poorly matched to
the reads that are being encoded, good compression can still be achieved.

[Faster sequence alignment through GPU-accelerated restriction of the seed-
and-extend search space](http://biorxiv.org/content/early/2014/08/01/007641)

Salzberg and colleagues going into GPU space.

> Motivation: In computing pairwise alignments of biological sequences,
software implementations employ a variety of heuristics that decrease the
computational effort involved in computing potential alignments. A key element
in achieving high processing throughput is to identify and prioritize
potential alignments where high-scoring mappings can be expected. These tasks
involve list-processing operations that can be efficiently performed on GPU
hardware. Results: We implemented a read aligner called A21 that exploits GPU-
based parallel sort and reduction techniques to restrict the number of
locations where potential alignments may be found. When compared with other
high-throughput aligners, this approach finds more high-scoring mappings
without sacrificing speed or accuracy. A21 running on a single GPU is about 10
times faster than comparable CPU-based tools; it is also faster and more
sensitive in comparison with other recent GPU-based aligners.

[Algorithms in Stringomics (I): Pattern-Matching against
"Stringomes"](http://biorxiv.org/content/early/2014/01/02/001669)

Paolo Ferragina usually does innovative work. Worth taking a look.

> This paper reports an initial design of new data-structures that generalizes
the idea of pattern- matching in stringology, from its traditional usage in an
(unstructured) set of strings to the arena of a well-structured family of
strings. In particular, the object of interest is a family of strings composed
of blocks/classes of highly similar ?stringlets,? and thus mimic a population
of genomes made by concatenating haplotype-blocks, further constrained by
haplotype-phasing. Such a family of strings, which we dub ?stringomes,? is
formalized in terms of a multi-partite directed acyclic graph with a source
and a sink. The most interesting property of stringomes is probably the fact
that they can be represented efficiently with compression up to their k-th
order empirical entropy, while ensuring that the compression does not hinder
the pattern-matching counting and reporting queries ? either internal to a
block or spanning two (or a few constant) adjacent blocks. The solutions
proposed here have immediate applications to next-generation sequencing
technologies, base-calling, expression profiling, variant-calling, population
studies, onco-genomics, cyber security trace analysis and text retrieval.

[Using 2k + 2 bubble searches to find SNPs in k-mer
graphs](http://biorxiv.org/content/early/2014/04/24/004507)

> Single Nucleotide Polymorphism (SNP) discovery is an important preliminary
for understanding genetic variation. With current sequencing methods we can
sample genomes comprehensively. SNPs are found by aligning sequence reads
against longer assembled references. De Bruijn graphs are efficient data
structures that can deal with the vast amount of data from modern
technologies. Recent work has shown that the topology of these graphs captures
enough information to allow the detection and characterisation of genetic
variants, offering an alternative to alignment-based methods. Such methods
rely on depth-first walks of the graph to identify closing bifurcations. These
methods are conservative or generate many false-positive results, particularly
when traversing highly inter-connected (complex) regions of the graph or in
regions of very high coverage. We devised an algorithm that calls SNPs in
converted De Bruijn graphs by enumerating 2k + 2 cycles. We evaluated the
accuracy of predicted SNPs by comparison with SNP lists from alignment based
methods. We tested accuracy of the SNP calling using sequence data from
sixteen ecotypes of Arabidopsis thaliana and found that accuracy was high. We
found that SNP calling was even across the genome and genomic feature types.
Using sequence based attributes of the graph to train a decision tree allowed
us to increase accuracy of SNP calls further. Together these results indicate
that our algorithm is capable of finding SNPs accurately in complex sub-graphs
and potentially comprehensively from whole genome graphs. The source code for
a C++ implementation of our algorithm is available under the GNU Public
Licence v3 at: https://github.com/redayounsi/2kplus2

[KmerStream: Streaming algorithms for k-mer abundance
estimation](http://biorxiv.org/content/early/2014/04/07/003962.1)

Paul Melsted.

> Motivation: Several applications in bioinformatics, such as genome
assemblers and error corrections methods, rely on counting and keeping track
of k-mers (substrings of length k). Histograms of k-mer frequencies can give
valuable insight into the underlying distribution and indicate the error rate
and genome size sampled in the sequencing experiment. Results: We present
KmerStream, a streaming algorithm for computing statistics for high throughput
sequencing data based on the frequency of k-mers. The algorithm runs in time
linear in the size of the input and the space requirement are logarithmic in
the size of the input. This very low space requirement allows us to deal with
much larger datasets than previously presented algorithms. We derive a simple
model that allows us to estimate the error rate of the sequencing experiment,
as well as the genome size, using only the aggregate statistics reported by
KmerStream and validate the accuracy on sequences from a PhiX control. As an
application we show how KmerStream can be used to compute the error rate of a
DNA sequencing experiment. We run KmerStream on a set of 2656 whole genome
sequenced individuals and compare the error rate to quality values reported by
the sequencing equipment. We discover that while the quality values alone are
largely reliable as a predictor of error rate, there is considerable
variability in the error rates between sequencing runs, even when accounting
for reported quality values. Availability: The tool KmerStream is written in
C++ and is released under a GPL license. It is freely available at
https://github.com/pmelsted/KmerStream

[SplitMEM: Graphical pan-genome analysis with suffix
skips](http://biorxiv.org/content/early/2014/04/06/003954)

Michael Schatz.

> Motivation: With the rise of improved sequencing technologies, genomics is
expanding from a single reference per species paradigm into a more
comprehensive pan-genome approach with multiple individuals represented and
analyzed together. One of the most sophisticated data structures for
representing an entire population of genomes is a compressed de Bruijn graph.
The graph structure can robustly represent simple SNPs to complex structural
variations far beyond what can be done from linear sequences alone. As such
there is a strong need to develop algorithms that can efficiently construct
and analyze these graphs. Results: In this paper we explore the deep
topological relationships between the suffix tree and the compressed de Bruijn
graph. We introduce a novel O(n log n) time and space algorithm called
splitMEM, that directly constructs the compressed de Bruijn graph for a pan-
genome of total length n. To achieve this time complexity, we augment the
suffix tree with suffix skips, a new construct that allows us to traverse
several suffix links in constant time, and use them to efficiently decompose
maximal exact matches (MEMs) into the graph nodes. We demonstrate the utility
of splitMEM by analyzing the pan- genomes of 9 strains of Bacillus anthracis
and 9 strains of Escherichia coli to reveal the properties of their core
genomes. Availability: The source code and documentation are available open-
source at http://splitmem.sourceforge.net

[MUSIC: A Hybrid Computing Environment for Burrows-Wheeler Alignment for
Massive Amount of Short Read Sequence Data](http://arxiv.org/abs/1402.0632)

> High-throughput DNA sequencers are becoming indispensable in our
understanding of diseases at molecular level, in marker-assisted selection in
agriculture and in microbial genetics research. These sequencing instruments
produce enormous amount of data (often terabytes of raw data in a month) that
requires efficient analysis, management and interpretation. The commonly used
sequencing instrument today produces billions of short reads (upto 150 bases)
from each run. The first step in the data analysis step is alignment of these
short reads to the reference genome of choice. There are different open source
algorithms available for sequence alignment to the reference genome. These
tools normally have a high computational overhead, both in terms of number of
processors and memory. Here, we propose a hybrid-computing environment called
MUSIC (Mapping USIng hybrid Computing) for one of the most popular open source
sequence alignment algorithm, BWA, using accelerators that show significant
improvement in speed over the serial code.

[Alignment-free comparison of next-generation sequencing data using
compression-based distance measures](http://arxiv.org/abs/1402.0640)

> Enormous volumes of short reads data from next-generation sequencing (NGS)
technologies have posed new challenges to the area of genomic sequence
comparison.

The multiple sequence alignment approach is hardly applicable to NGS data due
to the challenging problem of short read assembly.

Thus alignment-free methods need to be developed for the comparison of NGS
samples of short reads.

Recently, new k-mer based distance measures such as {\it CVTree}, dS2, {\it
co-phylog} have been proposed to address this problem.

However, those distances depend considerably on the parameter k, and how to
choose the optimal k is not trivial since it may depend on different aspects
of the sequence data.

Hence, in this paper we consider an alternative parameter-free approach:
compression-based distance measures.

These measures have shown impressive performance on long genome sequences in
previous studies, but they have not been tested on NGS short reads.

In this study we perform extensive validation and show that the compression-
based distances are highly consistent with those distances obtained from the
k-mer based methods, from the alignment-based approach, and from existing
benchmarks in the literature.

Moreover, as these measures are parameter-free, no optimization is required
and they still perform consistently well on multiple types of sequence data,
for different kinds of species and taxonomy levels.

The compression-based distance measures are assembly-free, alignment-free,
parameter-free, and thus represent useful tools for the comparison of long
genome sequences and NGS samples of short reads.

[Linear Recognition of Almost Interval Graphs](http://arxiv.org/abs/1403.1515)

Yixin Cao

> Let interval+kv, interval+ke, and interval?ke denote the classes of graphs
that can be obtained from some interval graph by adding k vertices, adding k
edges, and deleting k edges, respectively. When k is small, these graph
classes are called almost interval graphs. They are well motivated from
computational biology, where the data ought to be represented by an interval
graph while we can only expect an almost interval graph for the best. For any
fixed k, we give linear-time algorithms for recognizing all these classes, and
in the case of membership, our algorithms provide also a specific interval
graph as evidence. When k is part of the input, these problems are also known
as graph modification problems, all NP-complete. Our results imply that they
are fixed-parameter tractable parameterized by k, thereby resolving the long-
standing open problem on the parameterized complexity of recognizing
interval+ke, first asked by Bodlaender et al. [Bioinformatics, 11:49--57,
1995]. Moreover, our algorithms for recognizing interval+kv and interval?ke
run in times O(6k?(n+m)) and O(8k?(n+m)), (where n and m stand for the numbers
of vertices and edges respectively in the input graph,) significantly
improving the O(k2k?n3m)-time algorithm of Heggernes et al. [STOC 2007] and
the O(10k?n9)-time algorithm of Cao and Marx [SODA 2014] respectively.

[Indexing large genome collections on a PC](http://arxiv.org/abs/1403.7481)

Agnieszka Danek, Sebastian Deorowicz, Szymon Grabowski

> Motivation: The availability of thousands of invidual genomes of one species
should boost rapid progress in personalized medicine or understanding of the
interaction between genotype and phenotype, to name a few applications. A key
operation useful in such analyses is aligning sequencing reads against a
collection of genomes, which is costly with the use of existing algorithms due
to their large memory requirements.

Results: We present MuGI, Multiple Genome Index, which reports all occurrences
of a given pattern, in exact and approximate matching model, against a
collection of thousand(s) genomes. Its unique feature is the small index size
fitting in a standard computer with 16--32\,GB, or even 8\,GB, of RAM, for the
1000GP collection of 1092 diploid human genomes. The solution is also fast.
For example, the exact matching queries are handled in average time of 39\,?s
and with up to 3 mismatches in 373\,?s on the test PC with the index size of
13.4\,GB. For a smaller index, occupying 7.4\,GB in memory, the respective
times grow to 76\,?s and 917\,?s.

Availability: Software and Suuplementary material: \url{this http URL}.

[SAMBLASTER: fast duplicate marking and structural variant read extraction

Gregory G. Faust, Ira M. Hall

> Motivation: Illumina DNA sequencing is now the predominant source of raw
genomic data, and data volumes are growing rapidly. Bioinformatic analysis
pipelines are having trouble keeping pace. A common bottleneck in such
pipelines is the requirement to read, write, sort and compress large BAM files
multiple times.

Results: We present SAMBLASTER, a tool that reduces the number of times such
costly operations are performed. SAMBLASTER is designed to mark duplicates in
read-sorted SAM files as a piped post-pass on DNA aligner output before it is
compressed to BAM. In addition, it can simultaneously output into separate
files the discordant read-pairs and/or split-read mappings used for structural
variant calling. As an alignment post-pass, its own runtime overhead is
negligible, while dramatically reducing overall pipeline complexity and
runtime. As a stand-alone duplicate marking tool, it performs significantly
better than PICARD or SAMBAMBA in terms of both speed and memory usage, while
achieving nearly identical results.

Availability: SAMBLASTER is open source C++ code and freely available from
this https URL

[Constructing String Graphs in External
Memory](http://arxiv.org/abs/1405.7520)

> In this paper we present an efficient external memory algorithm to compute
the string graph from a collection of reads, which is a fundamental data
representation used for sequence assembly.

Our algorithm builds upon some recent results on lightweight Burrows-Wheeler
Transform (BWT) and Longest Common Prefix (LCP) construction providing, as a
by-product, an efficient procedure to extend intervals of the BWT that could
be of independent interest.

We have implemented our algorithm and compared its efficiency against SGA-the
most advanced assembly string graph construction program.

