---
title: Very Helpful Preprocessing Module for Those Interested in Assembling Genomes
tags: []
categories:
- blog
---
![](https://pbs.twimg.com/profile_images/3502968604/c3e5abff8694fd290bf308f24a
0a1a3a_bigger.jpeg)
<!--more-->

Jared Simpson, the author of SGA paper, [mailed the following
note](https://groups.google.com/forum/#!msg/sga-
users/95dTwpJCARU/oKoq54EZqKwJ) to SGA community. Exercise for readers - can
you tell, which genome looks really odd
[here](https://dl.dropboxusercontent.com/u/8813551/preqc_report.pdf)?

>

Hi all,

For the past few months I have been working on a new component of SGA to
assist users with their assembly. This program, called 'preqc', attempts to
measure the quality of the input data and how easy or difficult assembling it
will be.

The output of the pipeline is a PDF containing plots. I've uploaded an example
report here:

<https://dl.dropboxusercontent.com/u/8813551/preqc_report.pdf>

My hope is that this report will help you explore your data, select an
assembly strategy (ie a program and its parameters) and troubleshoot when
things go wrong. The report contains plots that attempt to capture the
structure of the underlying genome (for example how repetitive it is) and also
capture data quality (for example the sequencing error rate).

At the end of this email is a brief description of each plot. I hope to get
the manuscript up on arXiv this week which contains much more information.
Feel free to ask questions if anything is unclear.

Here are the instructions to run this on your data:

1) update to latest sga on github

2) preprocess the data:

sga preprocess --pe-mode 1 input_1.fastq input_2.fastq > my_genome.fastq

3) index the data

sga index -a ropebwt -t 8 --no-reverse my_genome.fastq

4) run preqc

sga preqc -t 8 my_genome.fastq > my_genome.preqc

5) make the report

/path/to/sga/src/bin/sga-preqc-report.py my_genome.preqc
/path/to/sga/src/examples/preqc/*.preqc

The preqc step only takes a few hours to run on very large genomes so it
should not be a burden to generate this report at the start of a project.

The goal of this project is to make assembly an easier and more predictable
process. I hope you all find this to be useful, even if you prefer to use a
different assembler.

Please let me know if you have any comments or suggestions!

Cheers,

Jared

Description of plots in the report:

\- Genome Size

This plot contains an estimate of the genome size based on k-mer count
statistics

\- Frequency of Variant Branches in the k-de Bruijn graph

This shows how often a de Bruijn graph branches due to sequence variation (ie
a SNP or indel) as a function of k. Most assemblers contain 'bubble popping'
algorithms to resolve sequence variants in the graph. These algorithms often
work well but a high branch rate makes assembly more difficult. The oyster
data branches very frequently due to variants making it difficult to assemble.

\- Frequency of Repeat Branches in the k-de Bruijn graph

This measures how often a de Bruijn graph branches due to repeats in the
genome. Repeat branches tend to be difficult to resolve. This is a key
indicator of how difficult the assembly will be.

\- Frequency of Error Branches in the k-de Bruijn graph

Like the above two plots, except it measures how often branches caused by
sequencing errors are encountered. These branches tend to be easier to get
handle during assembly.

\- Mean quality score by position

\- Fraction of bases at least Q30

These plots measure quality scores along the length of the read. The first
plot calculates the mean quality score at each base. The second calculates the
fraction of reads with quality >= Q30 at the base position.

\- k-mer position of first error

This measures sequencing error rate by looking for rare k-mers in the reads.
It is similar to how 'sga correct' finds and corrects errors. The plot shows
how often putatively incorrect k-mers are found at each position in the reads.

\- Per-position error rate

This directly measures the sequencing error rate along the read by counting
mismatches in groups of overlapping reads.

\- Duplicate proportion

This plot attempts to infer the proportion of read pairs that are PCR
duplicates.

\- Estimated fragment size histogram

This plot shows the distribution of paired-end fragment sizes.

\- 51-mer count distribution

For an assembly to be successful, it is important to have high coverage data.
This plot attempts to capture sequence coverage by plotting a histogram of
51-mer counts. Most data sets are bimodal with a sharp peak at low count for
k-mers with sequencing errors and a wider distribution of true genomic k-mers.
If these two distributions (true k-mers and k-mers with errors) are well-
separated, it makes assembly easier. The Snake data is ideal in this regard.
The yeast data is acceptable but would benefit from higher coverage.

\- GC Bias plots

This series of plots (one per data set) shows k-mer counts as function of GC
content in the read. Ideally, there would be no dependence between GC content
and k-mer count. The yeast data shows some bias, while the fish data is less
biased.

\- Simulated contig lengths in k-de Bruijn graph

The last plot shows a simulated assembly of the data by finding contig paths
in the graph. The simulator will extend contigs by ignoring sequencing errors
and resolving sequence variants, only stopping when a repeat is found or there
is no coverage. This plot can help predict if your data is easy to assemble or
hard. For example the yeast data is easy to assemble (very good N50) but the
oyster data, which has many sequence variant branches and many repeats, is
very hard (low N50).

