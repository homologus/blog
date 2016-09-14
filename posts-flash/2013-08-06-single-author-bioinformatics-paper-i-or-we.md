---
title: Single Author Bioinformatics Paper - 'I' or 'We'?
tags: []
categories:
- blog
---
Few recent examples:
<!--more-->

[Accelerated Profile HMM Searches - Sean R. Eddy](http://www.ploscompbiol.org/
article/info%3Adoi%2F10.1371%2Fjournal.pcbi.1002195)

It is safe to categorize it under 'I'.

> Profile hidden Markov models (profile HMMs) and probabilistic inference
methods have made important contributions to the theory of sequence database
homology search. However, practical use of profile HMM methods has been
hindered by the computational expense of existing software implementations.
Here **I** describe an acceleration heuristic for profile HMMs, the multiple
segment Viterbi (MSV) algorithm. The MSV algorithm computes an optimal sum of
multiple ungapped local alignment segments using a striped vector-parallel
approach previously described for fast Smith/Waterman alignment. MSV scores
follow the same statistical distribution as gapped optimal local alignment
scores, allowing rapid evaluation of significance of an MSV score and thus
facilitating its use as a heuristic filter. **I** also describe a 20-fold
acceleration of the standard profile HMM Forward/Backward algorithms using a
method **I** call sparse rescaling. These methods are assembled in a pipeline
in which high-scoring MSV hits are passed on for reanalysis with the full HMM
Forward/Backward algorithm. This accelerated pipeline is implemented in the
freely available HMMER3 software package. Performance benchmarks show that the
use of the heuristic MSV filter sacrifices negligible sensitivity compared to
unaccelerated profile HMM searches. HMMER3 is substantially more sensitive and
100- to 1000-fold faster than HMMER2. HMMER3 is now about as fast as BLAST for
protein searches.

[Aligning sequence reads, clone sequences and assembly contigs with BWA-MEM -
Heng Li](http://arxiv.org/pdf/1303.3997v2.pdf)

We bordering on 'passive'.

> BWA-MEM is a new alignment algorithm for aligning sequence reads or assembly
contigs against a large reference genome such as human. It automatically
chooses between local and end-to-end alignments, supports paired-end reads and
performs chimeric alignment. The algorithm is robust to sequencing errors and
applicable to a wide range of sequence lengths from 70bp to a few megabases.
For mapping 100bp sequences, BWA-MEM shows better performance than several
state-of-art read aligners to date.

[Exploring Genome Characteristics and Sequence Quality Without a Reference -
Jared T. Simpson](http://arxiv.org/pdf/1307.8026v1.pdf)

We paper with only one 'my'.

> The availability of inexpensive DNA sequence data has led to a vast increase
in the number of genome projects. For example, the Genome10K project [1] aims
to sequence 10,000 vertebrate genomes in the upcoming years. Despite the
advances in the production of DNA sequence data, performing de novo assembly
remains a signi cant challenge. This challenge was highlighted by the recent
Assemblathon2 project [2]. In this competition sequence data was obtained for
three vertebrate genomes. Twenty-one teams contributed assemblies of the three
genomes, producing 43 assemblies in total. The quality of the assemblies were
highly variable both between submissions for the same genome and within
individual software packages across the three species. In **my** view, this
variability stems from the practical diculty of designing an assembly
strategy (for instance, selecting software and its parameters) when little is
known about the structure of the underlying genome and the quality of the
available data. This paper aims to address this uncertainty.

What do you prefer?

\--------------------

Edit.

Twitter replies:

![Capture3](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture31-300x120.png)

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture23-300x63.png)

![Capture1](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture11-300x54.png)

