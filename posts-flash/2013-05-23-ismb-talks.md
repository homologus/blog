---
title: ISMB - Accepted Talks
tags: []
categories:
- blog
---
[ISMB talks](http://www.iscb.org/cms_addon/conferences/ismbeccb2013/proceeding
sbyarea.php) are announced. h/t: @nextgenseek
<!--more-->

Following talks may be of interest to our readers.

**Haplotype assembly in polyploid genomes and identical by descent shared tracts**

Author: Derek Aguiar , Brown University, United States

Additional authors:

Sorin Istrail, Brown University,

We already [covered this excellent work in our
blog](http://www.homolog.us/blogs/blog/2012/08/28/hapcompass-an-elegant-use-
of-graphs-for-haplotype-assemblyphasing/). So, we are not including the
abstract here.

\-----------------

**IDBA-Tran: A More Robust de novo de Bruijn Graph Assembler for Transcriptomes with Uneven Expression Levels**

Author: Yu Peng , The University of Hong Kong, Hong Kong

Additional authors:

Henry C.M. Leung, The University of Hong Kong,

S.M. Yiu, The University of Hong Kong,

Xin-Guang Zhu, Shanghai Institutes for Biological Sciences,

Ming-Zhu Lv, Shanghai Institutes for Biological Sciences,

Francis Chin, The University of Hong Kong,

This is the RNAseq version of IDBA work by Yu Peng and co-authors. IDBA makes
elegant use of multiple k-mers to improve a de Bruijn graph-based genome
assembly. Please take a look at our earlier commentary - [From Multiple Kmers
to Multi-kmer de Bruijn Graph](http://www.homolog.us/blogs/blog/2012/10/10
/multi-kmer-de-bruijn-graphs/).

Availability: http://www.cs.hku.hk/~alse/idba_tran

\--------------------

**Using State Machines to Model the IonTorrent Sequencing Process and Improve Read Error-Rates**

Author: David Golan , Tel Aviv University, Israel

Additional authors:

Paul Medvedev, The Pennsylvania State University.

>

Presentation Overview:

Motivation: The importance of fast and affordable DNA sequencing methods for
current day life sciences, medicine and biotechnology is hard to overstate. A
major player is IonTorrent, a pyrosequencing-like technology which produces
flowgrams sequences of incorporation values which are converted into
nucleotide sequences by a base-calling algorithm. Because of its exploitation
of ubiquitous semiconductor technology and innovation in chemistry, IonTorrent
has been gaining popularity since its debut in 2011. Despite the advantages,
however, IonTorrent read accuracy remains a significant concern. Results: We
present FlowgramFixer, a new algorithm for converting flowgrams into reads.
Our key observation is that the incorporation signals of neighboring flows,
even after normalization and phase correction, carry considerable mutual
information and are important in making the correct base-call. We therefore
propose that base-calling of flowgrams should be done on a read-wide level,
rather than one flow at a time. We show that this can be done in linear time
by combining a state machine with a Viterbi algorithm to find the nucleotide
sequence that maximizes the likelihood of the observed flowgram. FlowgramFixer
is applicable to any flowgram based sequencing platform. We demonstrate
FlowgramFixers superior performance on Ion Torrent E.Coli data, with a 4.8%
improvement in the number of high-quality mapped reads and a 7.1% improvement
in the number of uniquely mappable reads. Availability: Binaries and source
code of FlowgramFixer are freely available at:
http://www.cs.tau.ac.il/davidgo5/flowgramfixer.html

\----------------------

**Compressive genomics for protein databases**

Author: Noah Daniels , Tufts University, United States

> Presentation Overview:

Motivation: The exponential growth of protein sequence databases has
increasingly made the fundamental question of searching for homologs a
computational bottleneck. The amount of unique data, however, is not growing
nearly as fast; we can exploit this fact to greatly accelerate homology
search. Acceleration of programs in the popular PSI/DELTA-BLAST family of
tools will not only speed up homology search directly, but also the huge
collection of other current programs that primarily interact with large
protein databases via precisely these tools. Results: We introduce a suite of
homology search tools, powered by compressively-accelerated protein BLAST
(CaBLASTP), which are significantly faster than and comparably accurate to all
known state- of-the-art tools including HHblits, DELTA-BLAST, and PSI-BLAST.
Further, our tools are implemented in a manner that allows direct substitution
into existing analysis pipelines. The key idea is that we introduce a local
similarity-based compression scheme that allows us to operate directly on the
compressed data. Importantly, CaBLASTPs runtime scales almost linearly in the
amount of unique data, as opposed to current BLASTP variants which scale
linearly in the size of the full protein database being searched. Our
compressive algorithms will speed up many tasks such as protein structure
prediction and orthology mapping which rely heavily on homology search.
Availability: CaBLASTP is available under the GNU Public License at
http://cablastp.csail.mit.edu/.

\-------------------------------

**Short Read Alignment with Populations of Genomes**

Author: Lin Huang , Stanford University, United States

> Presentation Overview:

The increasing availability of high throughput sequencing technologies has led
to thousands of human genomes having been sequenced in the past years. Efforts
such as the 1000 Genomes Project further add to the availability of human
genome variation data. However, to-date there is no method that can map reads
of a newly sequenced human genome to a large collection of genomes. Instead,
methods rely on aligning reads to a single reference genome. This leads to
inherent biases and lower accuracy. To tackle this problem, a new alignment
tool BWBBLE is introduced in this paper. We (1) introduce a new compressed
representation of a collection of genomes, which explicitly tackles the
genomic variation observed at every position, and (2) design a new alignment
algorithm based on the Burrows-Wheeler transform that maps short reads from a
newly sequenced genome to an arbitrary collection of 2 or more (up to millions
of) genomes with high accuracy and no inherent bias to one specific genome.

The above talk comes from Serafim Batzoglou's group. Serafim worked on ARACHNE
assembler a decade back with Lander, and then joined Stanford. His LAGAN
aligner was used in [the first ENCODE project](http://www.nature.com/nature/jo
urnal/v447/n7146/full/nature05874.html).

\-----------------------

**Design of Shortest Double-Stranded DNA Sequences Covering All K-mers with Applications to Protein Binding Microarrays and Synthetic Enhancers**

Author: Yaron Orenstein , Tel-Aviv University, Israel

> Presentation Overview:

Novel technologies can generate large sets of short double-stranded DNA
sequences that can be used to measure their regulatory effects. Microarrays
can measure in vitro the binding intensity of a protein to thousands of
probes. Synthetic enhancer sequences inserted into an organism's genome allow
us to measure in vivo the effect of such sequences on the phenotype. In both
applications, by using sequence probes that cover all k-mers, a comprehensive
picture of the effect of all possible short sequences on gene regulation is
obtained. The value of k that can be used in practice is, however, severely
limited by cost and space considerations. A key challenge is therefore to
cover all k-mers with a minimal number of probes.The standard way to do this
uses the de Bruijn sequence of length 4^k. However, since probes are double
stranded, when a k-mer is included in a probe, its reverse complement k-mer is
accounted for as well. Here we show how to efficiently create a shortest
possible sequence with the property that it contains each k-mer or its reverse
complement, but not necessarily both. The length of the resulting sequence
approaches half that of the de Bruijn sequence as k increases. By reducing the
total sequence length, experimental limitations can be overcome;
alternatively, additional sequences with redundant k-mers of interest can be
added.

\-----------------------

**Poly(A) motif prediction using spectral latent features from human DNA sequences**

Author: Bo Xie , Georgia Institute of Technology, United States

Additional authors:

Boris Yankovic, King Abdullah University of Science and Technology,

Vladimir Bajic, King Abdullah University of Science and Technology,

Le Song, Georgia Institute of Technology,

Xin Gao, King Abdullah University of Science and Technology,

> Presentation Overview:

Motivation: Polyadenylation is the addition of a poly(A) tail to an RNA
molecule. Identifying DNA sequence motifs that signal the addition of poly(A)
tails is essential to improved genome annotation and better understanding of
the regulatory mechanisms and stability of mRNA. Existing poly(A) motif
predictors demonstrate that information extracted from the surrounding
nucleotide sequences of candidate poly(A) motifs can differentiate true motifs
from the false ones to a great extent. A variety of sophisticated features has
been explored, including sequential, structural, statistical, thermodynamic
and evolutionary properties. However, most of these methods involve extensive
manual feature engineering, which can be time-consuming and can require in-
depth domain knowledge. Results: We propose a novel machine learning method
for poly(A) motif prediction by marrying generative learning (hidden Markov
models) and discriminative learning (support vector machines). Generative
learning provides a rich palette on which the uncertainty and diversity of
sequence information can be handled, while discriminative learning allows the
performance of the classification task to be directly optimized. Here, we
employed hidden Markov models for fitting the DNA sequence dynamics, and
developed an efficient spectral algorithm for extracting latent variable
information from these models. These spectral latent features were then fed
into support vector machines to fine tune the classification performance. We
evaluated our proposed method on a comprehensive human poly(A) dataset that
consists of 14,740 samples from 12 of the most abundant variants of human
poly(A) motifs. Compared with one of previous state-of-art methods in the
literature (the random forest model with expert-crafted features), our method
reduces the average error rate, false negative rate and false positive rate by
26%, 15% and 35%, respectively. Meanwhile, our method made about 30% fewer
error predictions relative to the other string kernels. Furthermore, our
method can be used to visualize the importance of oligomers and positions in
predicting poly(A) motifs, from which we can observe a number of
characteristics in the surrounding regions of true and false motifs that have
not been reported before. Availability:
website:http://sfb.kaust.edu.sa/Pages/Software.aspx

