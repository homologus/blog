---
title: Efficient de novo Assembly of Highly Heterozygous Genomes from Whole-genome
  Shotgun Short Reads
tags: []
categories:
- blog
---
Our readers will surely find [this paper
interesting](http://genome.cshlp.org/content/early/2014/04/22/gr.170720.113)
(h/t: @ErichMScwartz). We have not read it yet, but plan to do so shortly.
<!--more-->

> Although many de novo genome assembly projects have recently been performed
using high-throughput sequencers, assembling the highly heterozygous diploid
genomes is a big scientific challenge due to the increased complexity of the
de Bruijn graph structure predominantly employed. To deal with an increasing
demand for sequencing of non-model and/or wild-type sample, in most cases,
inbred lines or fosmid-based hierarchical sequencing methods are employed with
overcoming such problems. However, these methods are costly and time
consuming, forfeiting the advantage of massive parallel sequencing. Here, we
describe a novel de novo assembler, Platanus, which can effectively manage
high-throughput data from heterozygous samples. Platanus assembles DNA
fragments (reads) into contigs by constructing de Bruijn graphs with
automatically optimized k-mer sizes, followed by scaffolding of contigs based
on paired-end information. The complicated graph structures that result from
the heterozygosity are simplified during not only the contig assembly step but
also the scaffolding step. We evaluated the assembly results on eukaryotic
samples with various levels of heterozygosity. Compared with other assemblers,
the Platanus assembly results have a larger NG50 length without any
accompanying loss of accuracy in both simulated data and real data. In
addition, Platanus recorded the largest NG50 values for two of the three low
heterozygous species used in the de novo assembly contest, Assemblathon2.
Platanus provides, therefore, a novel and efficient approach for the assembly
of Giga base-sized highly heterozygous genomes and is also an attractive
alternative to the existing assemblers designed for genomes of lower
heterozygosity.

Their website can be accessed [here](http://platanus.bio.titech.ac.jp
/platanus-assembler/).

> Platanus is a completely newly developed de novo genome assembler for high-
throughput sequence data (mainly illuminas data), which is designed to
assemble GB-size class genome. The greatest characteristics of Platanus
assembler is the ability to manage highly heterozygous samples. Platanus
assembles DNA fragments (reads) into contiguous sequences (contigs)
constructing de Bruijn graphs with multiple k-mer sizes and constructing
scaffolds from contigs based on paired-end information. The complicated graph
structures caused by heterozygosity are simplified during both contig assembly
and scaffolding.

What else is out there? Here is only a subset of previous discussions on the
topic.

[Hapsembler An Assembler for Highly Polymorphic
Genomes](http://www.homolog.us/blogs/blog/2013/02/07/hapsembler-an-assembler-
for-highly-polymorphic-genomes/)

[HaploMerger: A Software Tool for Assembling Highly Polymorphic
Genomes](http://www.homolog.us/blogs/blog/2012/07/11/haplomerger-a-software-
tool-for-assembling-highly-polymorphic-genomes/)

[dipSpades Beats Haplomerger Hands Down in Diploid
Assembly](http://www.homolog.us/blogs/blog/2014/03/04/dipspades-beats-
haplomerger-hands-diploid-assembly/)

[High-throughput Microbial Population Genomics using the Cortex Variation
Assembler](http://www.homolog.us/blogs/blog/2013/01/11/high-throughput-
microbial-population-genomics-using-the-cortex-variation-assembler/)

Please note that you do not have to restrict yourself to de Bruijn graphs. If
everything else fails, [contact Jason Chin to order long
reads](http://www.homolog.us/blogs/blog/2014/03/24/pacbio-jason-chins-agbt-
presentation-on-diploid-assembly/) :)

