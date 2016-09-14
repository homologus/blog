---
title: Nanopore Assembly Improves with HMM Polishing of Signal Level Data
tags: []
categories:
- blog
---
A few days back, we [posted](http://www.homolog.us/blogs/blog/2015/02/20/e
-coli-genome-assembled-using-nanopore-data-only/) about assembly of E. coli
genome from using nanopore-only data. At that time, Jared Simpson, the
corresponding author, tweeted about including information on error-correcting
based on the actual electrical signals instead of nucleotide data in a later
version of the paper. Today he notified that the new version has been uploaded
in arxiv. The changes in abstract are emphasized below, and it is great that
the accuracy is now at 99.4%.
<!--more-->

[A complete bacterial genome assembled de novo using only nanopore sequencing
data](http://biorxiv.org/content/early/2015/03/11/015552)

> A method for de novo assembly of data from the Oxford Nanopore MinION
instrument is presented which is able to reconstruct the sequence of an entire
bacterial chromosome in a single contig. Initially, overlaps between nanopore
reads are detected. Reads are then subjected to one or more rounds of error
correction by a multiple alignment process employing partial order graphs.
After correction, reads are assembled using the Celera assembler. **Finally,
the assembly is polished using signal-level data from the nanopore employing a
novel hidden Markov model.** We show that this method is able to assemble
nanopore reads from Escherichia coli K-12 MG1655 into a single contig of
length 4.6Mb permitting a full reconstruction of gene order. The resulting
draft assembly has 98.4% nucleotide identity compared to the finished
reference genome. **After polishing the assembly with our signal-level HMM,
the nucleotide identity is improved to 99.4%.** We show that MinION sequencing
data can be used to reconstruct genomes without the need for a reference
sequence or data from other sequencing platforms.

