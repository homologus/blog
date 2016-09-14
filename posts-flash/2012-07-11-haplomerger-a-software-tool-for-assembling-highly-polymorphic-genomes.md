---
title: 'HaploMerger: A Software Tool for Assembling Highly Polymorphic Genomes'
tags:
- Polymorphic
categories:
- blog
---
A new paper [published in Genome Research](http://genome.cshlp.org/content/ear
ly/2012/07/01/gr.133652.111.abstract) caught our attention. It addresses the
issue of assembling highly polymorphic diploid genomes. You can read the
abstract [here at NCBI](http://www.ncbi.nlm.nih.gov/pubmed/22555592).
<!--more-->

Typically, when an NGS or traditional assembler puts together a genome from
raw reads, it assumes that the library contains nucleotides from an unique
genome. In reality, the reads consist of data from two distinct chromosomes.
If those two chromosomes are almost identical, assumption of unique genome
should work. For highly polymorphic diploid genomes, that basic assumption
breaks down leading to mis-assemblies and other problems. The situation gets
even worse for NGS reads, because the reads themselves are short and error-
prone.

One cool way to appreciate the polymorphism problem through simulation is

(i) take the assembled genomes or human and chimp,

(ii) extract synteny regions of about 100 Mbases from two genomes,

(iii) create simulated NGS libraries from those two selected regions by
choosing reads randomly,

(iv) Combine two libraries, and let Velvet or other assemblers assemble them.

Getting back to our original topic, HaploMerger addresses the issue of
assembling highly polymorphic genomes by creating a novel graph-based
structure called **diploid genome assembly (DGA) graph**. DGA graphs describe
and store the inter-relationships between alleles or

homologs in a diploid genome assembly.

Quoting the paper -

> When applied to three real polymorphic diploid assemblies, HaploMerger gave
comparable or better results than manual curation. The first two real
assemblies are from Ciona savignyi and Branchiostoma floridae, both of which
were generated from Sanger reads and accompanied by manually curated reference
haploid assemblies (Small et al. 2007; Putnam et al. 2008). The third real
assembly is from a single Chinese amphioxus (Branchiostoma belcheri),which was
produced in our laboratory using NGS technologies. Moreover, we compared the
B. belcheri haploid assemblies (and relevant data produced by HaploMerger)
with a large quantity of EST sequences and revealed that the two divergent
haplotypes from a single animal are highly complementary to each other.

The code is available as open source package from
[here](http://mosas.sysu.edu.cn/genome/download_softwares). We have not tried
it yet, but their approach seems very promising.

