---
title: SSP Transcriptome Assembler from Tehran, TIGER, PEGASAS Genome Assemblers
tags: []
categories:
- rnaseq
---
More genome and transcritome assembly methods are getting published than we
can keep track of. They all claim to be better than the existing ones. We are
reporting them for the time being without any detailed analysis.
<!--more-->

[Tiger: tiled iterative genome assembler and approximate multi-genome
aligner](https://www.ideals.illinois.edu/handle/2142/45618) (h/t:
@assemblathon)

> Sequence assembly and alignments are two important stepping stones for
comparative genomics. With the fast adoption of the next-generation sequencing
(NGS) technologies and the coming of the third-generation sequencing (TGS)
technologies, genomics has provided us with an unprecedented opportunity to
answer fundamental questions in biology and elucidate human diseases. However,
most de novo assemblers require an enormous amount of computational resource,
which is not readily available to most research groups and medical personnel.
Moreover, there has been little progress on sequence assembly qualities,
especially for genomes having high repetitions. As more affordable raw data
and assembled genomes are accessible to the community, there is an emerging
demand for genome searches among the big amount of divergent genomes in gene
banks. The genomes can be in the form of raw reads, unfinished/low-quality
assemblies, or completed genomes, on which traditional multi-sequence
alignment tools may not be suitable to perform similarity searches. Yet there
are few research studies aiming at meeting this demand. We have developed a
novel de novo assembly framework, called Tiger assembler, which adapts to
available computing resources by iteratively decomposing the assembly problem
into sub-problems. Our method can flexibly embed different assemblers for
various types of target genomes. Using the sequence data from a human
chromosome, our results show that Tiger can achieve much better NG50s, better
genome coverage, and slightly higher errors, as compared to Velvet and
SOAPdenovo, using a modest amount of memory that is available in commodity
computers today. We also experimented with a real de novo assembly, i.e., the
E. mexicana genome, and demonstrated the strength of our work. The N50s of our
contigs and scaffolds by Tiger were 7 and 57 times longer than those by
SOAPdenovo. On the other hand, the assembly done by ALLPATHS-LG had only one-
third genome size. We also developed a multi-genome sequence aligner, called
Tiger aligner, able to perform fast similarity checks among multiple genomes
with distant biological relationship and low quality raw data. Practical
applications of our tool are demonstrated through experiments. The performance
of Tiger aligner on traditional multi-sequence alignments is also compared
against existing works, MUMmer and SOAPaligner. The results show the
practicality and strengths of our tool. ? Most state-of-the-art assemblers
that can achieve relatively high assembly quality need an excessive amount of
computing resource (in particular, memory) that is not readily available to
most researchers. Tiger assembler provides the only known viable path to
utilize NGS de novo assemblers that require more memory than that is present
in available computers. Evaluation results demonstrate the feasibility of
getting better quality results with low memory footprint and the scalability
of using distributed commodity computers. The quantity explosion of genomes
makes existing multi-sequence aligners impractical to check similarities among
genomes with different characteristics in terms of evolutionary relationship
and sequence completeness. Current pairwise sequence aligners cannot cope with
them without big revisions because of the inherently algorithmic limitations.
Tiger aligner is the first known work invented to deal with the multi-genome
problems, leveraging the feature-based image.

\-------------------------------------------------------

In twitter, @srbehera11 forwarded us [a new RNA-seq algorithm
paper](http://www.ncbi.nlm.nih.gov/pubmed/24161398) from Tehran.

[SSP: An interval integer linear programming for de novo transcriptome
assembly and isoform discovery of RNA-seq
reads](http://www.ncbi.nlm.nih.gov/pubmed/24161398)

> Recent advances in the sequencing technologies have provided a handful of
RNA-seq datasets for transcriptome analysis. However, reconstruction of full-
length isoforms and estimation of the expression level of transcripts with a
low cost are challenging tasks. We propose a novel de novo method named SSP
that incorporates interval integer linear programming to resolve alternatively
spliced isoforms and reconstruct the whole transcriptome from short reads.
Experimental results show that SSP is fast and precise in determining
different alternatively spliced isoforms along with the estimation of
reconstructed transcript abundances. The SSP software package is available at
http://www.bioinf.cs.ipm.ir/software/ssp.

\-------------------------------------------------------

Here is another one from Ontario.

Link (h/t: @assemblathon)

> The enormous amount of short reads produced by next generation sequencing
(NGS) techniques such as Roche/454, Illumina/Solexa and SOLiD sequencing
opened the possibility of de novo genome assembly. Some of the de novo genome
assemblers (e.g., Edena, SGA) use an overlap graph approach to assemble a
genome, while others (e.g., ABySS and SOAPdenovo) use a de Bruijn graph
approach. Currently, the approaches based on the de Bruijn graph are the most
successful, yet their performance is far from being able to assemble entire
genomic sequences. We developed a new overlap graph based genome assembler
called Paired-End Genome ASsembly Using Short-sequences (PEGASUS) for paired-
end short reads produced by NGS techniques. PEGASUS uses a minimum cost
network flow approach to predict the copy count of the input reads more
precisely than other algorithms. With the help of accurate copy count and mate
pair support, PEGASUS can accurately unscramble the paths in the overlap graph
that correspond to DNA sequences. PEGASUS exhibits comparable and in many
cases better performance than the leading genome assemblers.

Edit. We are including relevant twitter discussions.

?

1\. @pathogenomenick said -

"@assemblathon hmm, numerous factual errors in the abstract!"

2\. @sebhtml pointed out that the above method is similar to:

[Maximum Likelihood Genome Assembly - Paul Medvedev1 and Michael
Brudno](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3154397/)

\-------------------------------------------------------

@assemblathon forwarded another one:

MS thesis:

[Genome Assembly: Scaffolding Guided by Related
Genomes](https://www.duo.uio.no/handle/10852/37431)

> Genomic research relies on computers to process large amounts of genomic
data. In order to digitize such data, the genomes have to be sequenced and
assembled. Modern sequencing technologies allow fast and inexpensive
sequencing. Sequencing machines produce multiple chunks of sequences called
reads, which are assembled into contigs, and then further into larger pieces
called scaffolds. The process of scaffolding contigs often requires obtaining
additional data through lab work, which is both time-consuming and expensive.
The purpose of this thesis is to assess whether contigs can be scaffolded with
the aid of previously sequenced related genomes, and whether the use of
multiple related genomes can increase the precision of the resulting
scaffolds. A pipeline with a simple, prototypical algorithm was developed to
process contigs using information from related genomes. This pipeline produces
scaffolds and provides an evaluation of these. Contigs from 4 bacterial
sequencing projects were scaffolded with 10 related genomes as guides for each
bacterium. The results showed that using multiple guiding genomes, which were
closely related to the target genome, enabled scaffolds to be produced with
few errors.

?@OmicsOmicsBlog comments:

@assemblathon a bit of an odd duck, in that little of the presented data is
relevant to supposed purpose (assessing with RAD markers)

