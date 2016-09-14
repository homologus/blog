---
title: 'STAR: Really Kick-ass RNA-seq Aligner'
tags: []
categories:
- blog
---
Stephen Turner's Getting Genetics Done blog
[posted](http://gettinggeneticsdone.blogspot.com/2012/11/star-ultrafast-
universal-rna-seq-aligner.html) on a new paper on ultrafast RNAseq aligning
that [came out in Bioinformatics](http://bioinformatics.oxfordjournals.org/con
tent/early/2012/10/25/bioinformatics.bts635.abstract). The speed of this
program is amazing, BUT forget about aligning human genome in your laptop with
this program. You need to have ~27GB of RAM, which is typical for servers
these days. The program comes from a group at Cold Spring Harbor Lab (yes, the
same place that solves the most difficult bioinformatics problems to [gamble
on interest rate swaps](http://www.homolog.us/blogs/2012/09/08/does-cold-
spring-harbor-lab-have-cancer/)).
<!--more-->

> To align our large (exceeding 80 billon reads) ENCODE Transcriptome RNA-seq
dataset we developed the Spliced Transcripts Alignment to a Reference (STAR)
software based on a previously un-described RNA-seq alignment algorithm which
utilizes sequential maximum mappable seed search in uncompressed suffix arrays
followed by seed clustering and stitching procedure. **STAR outperforms other
aligners by more than a factor of 50 in mapping speed, aligning to the human
genome 550 Million 2x76bp paired-end reads per hour on a modest 12-core
server, while at the same time improving alignment sensitivity and
precision.** In addition to unbiased de novo detection of canonical junctions,
STAR can discover non-canonical splices and chimeric (fusion) transcripts, and
is also capable of mapping full length RNA sequences. Using Roche 454
sequencing of RT-PCR amplicons, we experimentally validated 1,960 novel
intergenic splice junctions with an 80-90% success rate, corroborating the
high precision of the STAR mapping strategy.

The program and code are available freely. Sadly, the paper is not.

Here are few important links -

[Star code and example data](https://github.com/alexdobin/STAR)

[STAR Manual
](https://github.com/alexdobin/STAR/blob/master/doc/STARmanual.pdf)

**How to run (from those impatient to read manual)**

1\. **Each STAR run should be made from a fresh working directory. All the
output files are stored in the working directory. The output files will be
overwritten without a warning every time you run STAR.**

2\. Just like Bowtie, you need to first generate a genomic database.

`STAR --runMode genomeGenerate --genomeDir /path/to/GenomeDir
--genomeFastaFiles /path/to/genome/fasta1 /path/to/genome/fasta2 --runThreadN
`

Please keep in mind that for STAR, you can generate the database either in
regular mode or in 'splice junction mode' for better mapping of spliced reads.

3\. Run alignment

`STAR --genomeDir /path/to/GenomeDir --readFilesIn /path/to/read1
[/path/to/read2] --runThreadN  \-- `

4\. Another cool feature of STAR is that it loads the genomic database in
shared memory and keeps it there for concurrent alignment runs. That saves
time, if you finish one run and start another in near future.

