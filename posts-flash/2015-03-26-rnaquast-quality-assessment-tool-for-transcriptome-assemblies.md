---
title: 'rnaQUAST: Quality Assessment Tool for Transcriptome Assemblies'
tags: []
categories:
- blog
---
Algorithmic Biology Lab in St. Petersburg of SPAdes fame [developed a new
tool](http://bioinf.spbau.ru/en/rnaquast) for evaluating quality of
transcriptome assemblies using reference genome and annotation (h/t: anton).
Stay tuned for more information.
<!--more-->

>

3 Options

3.1 Input data options

To run rnaQuast one needs to provide either FASTA files with transcripts
(recommended), or align transcripts to the reference genome manually and
provide the resulting PSL files. rnaQUAST also requires reference genome and
optionally an annotation.

-r , --reference 

Single file with reference genome containing all chromosomes/scaffolds in
FASTA format.

-gtf , --annotation 

File with annotation in GTF/GFF format.

-c , --transcripts 

File(s) with transcripts in FASTA format separated by space.

-psl , --alignment 

File(s) with transcripts alignments in PSL format separated by space.

3.2 Basic options

-o , --output_dir 

Directory to store all results. Default is rnaQUAST_results/results_.

\--test

Run rnaQUAST on the test data from the test_data folder, output directory is
rnaOUAST_test_output.

-d, --debug 

Report detailed information, typically used only when detecting problems.

-h, --help 

Show help message and exit.

3.3 Advanced options

-t , --threads 

Maximum number of threads. Default is the number of CPU cores (detected
automatically).

-l , --labels 

Names of assemblies that will be used in the reports separated by space.

-ss, --strand_specific 

Set if transcripts were assembled using strand specific RNA-Seq data in order
to benefit from knowing whether the transcript originated from the + or -
strand.

\--min_alignment

Minimal alignment size to be used, default value is 50.

\--no_plots

Do not draw plots (makes rnaQUAST run a bit faster).

