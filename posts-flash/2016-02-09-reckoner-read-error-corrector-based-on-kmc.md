---
title: 'RECKONER: Read Error Corrector Based on KMC'
tags: []
categories:
- blog
---
Our readers are already familiar with the work of Sebastian Deorowicz and
colleagues for their innovative kmc2 kmer-counting program. In this new paper
[posted at arxiv](http://arxiv.org/abs/1602.03086), they used kmc2 to build an
error correction program.
<!--more-->

> Motivation: Next-generation sequencing tools have enabled producing of huge
amount of genomic information at low cost. Unfortunately, presence of
sequencing errors in such data affects quality of downstream analyzes.
Accuracy of them can be improved by performing error correction. Because of
huge amount of such data correction algorithms have to: be fast, memory-
frugal, and provide high accuracy of error detection and elimination for
variously-sized organisms.

Results: We introduce a new algorithm for genomic data correction, capable of
processing eucaryotic 300 Mbp-genome-size, high error-rated data using less
than 4 GB of RAM in less than 40 minutes on 16-core CPU. The algorithm allows
to correct sequencing data at better or comparable level than competitors.
This was achieved by using very robust KMC~2 k-mer counter, new method of
erroneous regions correction based on both k-mer counts and FASTQ quality
indicators as well as careful optimization. Availability: Program is freely
available at this http URL Contact: sebastian.deorowicz@polsl.pl

Another memory-efficient approach was published in
[LoRDEC](https://www.gatb.fr/software/lordec/), which used Rayan Chikhi et
al's GATB library.

