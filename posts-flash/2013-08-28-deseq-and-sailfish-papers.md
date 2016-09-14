---
title: DEseq and Sailfish Papers for RNAseq
tags: []
categories:
- rnaseq
---
Those working on statistical analysis of RNAseq data will find the following
two papers useful.
<!--more-->

1\. **DESeq and edgeR:**

[Count-based differential expression analysis of RNA sequencing data using R
and Bioconductor](http://www.nature.com/nprot/journal/v8/n9/full/nprot.2013.09
9.html)

> RNA sequencing (RNA-seq) has been rapidly adopted for the profiling of
transcriptomes in many areas of biology, including studies into gene
regulation, development and disease. Of particular interest is the discovery
of differentially expressed genes across different conditions (e.g., tissues,
perturbations) while optionally adjusting for other systematic factors that
affect the data-collection process. There are a number of subtle yet crucial
aspects of these analyses, such as read counting, appropriate treatment of
biological variability, quality control checks and appropriate setup of
statistical modeling. Several variations have been presented in the
literature, and there is a need for guidance on current best practices. This
protocol presents a state-of-the-art computational and statistical RNA-seq
differential expression analysis workflow largely based on the free open-
source R language and Bioconductor software and, in particular, on two widely
used tools, DESeq and edgeR. Hands-on time for typical small experiments
(e.g., 410 samples) can be <1 h, with computation time <1 d using a standard
desktop PC.

The related application note at bioconductor can be found here: [Di fferential
analysis of count data - the DESeq2 package](http://bioconductor.org/packages/
2.13/bioc/vignettes/DESeq2/inst/doc/DESeq2.pdf)

\------------------------------------

2\. **Sailfish**

[Sailfish: Alignment-free Isoform Quantification from RNA-seq Reads using
Lightweight Algorithms](http://arxiv.org/abs/1308.3700)

> RNA-seq has rapidly become the de facto technique to measure gene
expression. However, the time required for analysis has not kept up with the
pace of data generation. Here we introduce Sailfish, a novel computational
method for quantifying the abundance of previously annotated RNA isoforms from
RNA-seq data. Sailfish entirely avoids mapping reads, which is a time-
consuming step in all current methods. Sailfish provides quantification
estimates much faster than existing approaches (typically 20-times faster)
without loss of accuracy.

It is an alignment-free method that saves space and time. They use perfect
hash on k-mers and determines the expression distribution. Next Gen Seek blog
explains the algorithm over a cup of coffee. The code can be downloaded from
[this link](http://www.cs.cmu.edu/~ckingsf/software/sailfish/downloads.html).
We created a [Sailfish wiki
page](http://homolog.us/wiki1/index.php?title=Sailfish) to go over the code,
when we find time.

[Sailfish: Isoform Quantitation at the Speed of Making a Cup of
Coffee](http://nextgenseek.com/2013/08/sailfish-isoform-quantitation-at-the-
speed-of-making-a-cup-of-coffee/)

> It is easy to see that the alignment step and the EM step are the huge
bottlenecks in RNA-seq isoform analysis. The complexity in alignment and EM
steps, grow exponentially as we sequence more reads. And this makes isoform
quantitation time and resource consuming. For example, assuming things
converge at the same rate, by doubling the read depth, the time to align
doubles and the EM matrix size also doubles. In reality, with larger alignment
profile, the convergence time also increases significantly.

This is where Sailfish comes to help. Sailfish kind of simplified the
computational bottlenecks by simply taking the alignment process away.
Sailfish starts with a known transcriptome and creates unique k-mer index from
the reference transcriptome. Then it runs through each sequenced read and
catalogs the kmer counts in the read. Essentially this is the alignment-step.
Instead of doing a real alignment, it keeps a record of k-mers from RNA-seq
reads if they are present in the reference k-mer index. For example, a 100
base read can create 81, 20-mers and it will increase count for corresponding
20-mer, if it is present in the reference k-mer index. At the end of the k-mer
indexing process, for each unique k-mer in the reference transcriptome we get
counts observed in the RNA-seq data.

Human reference transcriptome has over 60 Million k-mers of size 20 bases and
of these close to 40 Million k-mers appear at least once. And in the data that
they used there were only about 150,000 distinct k-mer equivalent classes with
non-zero counts. This makes EM sparse matrix in Sailfish almost a constant
size; ~150K x number of human transcripts. And the size does not grow
exponentially with RNA-seq data depth. With the help of SQUAREM, Sailfish
could make the convergence of EM even faster. The result is an isoform
quantitation method that is super-fast and not memory hogging. Check the
figure from the paper below that compares the alignment plus quantitation
speed of RSEM, eXpress, an Cufflinks with Sailfish. On the real data, Sailfish
finished in just about 10 mins, while RSEM running complete EM on all reads
took close to 47 hours.

Also, Lior Pachter [covered the algorithm in a blog
post](http://liorpachter.wordpress.com/2013/08/20/sailfish/).

> The results of the paper are impressive. They compare speed and accuracy
with RSEM, Cufflinks and eXpress and obtain comparable accuracy while avoiding
the time intensive alignment of reads to transcripts (or the genome in the
case of Cufflinks). An interesting point made is that bias can be corrected
after fragment assignment (or in the case of Sailfish after k-mer assignment)
without much loss in accuracy. We used a similar approximation in eXpress,
namely stopping estimation of bias parameters after 5 million reads have been
processed, but it seems that postponing the entire correction until fragment
assignment is complete is acceptable.

Sailfish also appears to have been well engineered. The code (in C++) is well
documented and available in both source and executable (for Linux and Mac OS
X). I havent had a chance to test it yet but hope to do so soon.

