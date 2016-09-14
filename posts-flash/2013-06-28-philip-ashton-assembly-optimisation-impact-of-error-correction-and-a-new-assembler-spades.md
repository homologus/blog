---
title: 'Philip Ashton: Assembly Optimisation &ndash; Impact of Error Correction and
  a New Assembler, SPAdes'
tags: []
categories:
- blog
---
Philip Ashton (@flashton2003 in Twitter) is a post-doctoral researcher working
on bioinformatics at Public Health England. He [started to write the Bits and
Bugs blog in May](http://www.homolog.us/blogs/blog/2013/05/02/assessment-of-
assembly/). He is one of those rare bioinformaticians interested in genome and
transcriptome assembly.
<!--more-->

You will enjoy [his new blog post](http://bitsandbugs.org/2013/06/28/assembly-
optimisation-impact-of-error-correction-and-a-new-assembler-spades/), where he
shows how much the assemblies improve with an error-correction step. Also, he
includes SPAdes in his comparison. We have not seen many comparisons with
SPAdes elsewhere apart from by GAGE and the authors of SPAdes themselves.

Maybe [MaSurCA](http://www.homolog.us/blogs/blog/2013/05/14/how-about-a
-chaotic-genome-assembler/) next?

\---------------------------------------------------------------------

**Assembly optimisation impact of error correction and a new assembler, SPAdes**

We have seen[ significant differences between assemblies of shiga toxinigenic
E. coli genomes where the DNA was extracted with different
protocols](http://bitsandbugs.org/2013/06/25/assembly-difference-due-to-dna-
extraction-method/). In those experiments, I used Velvet for assembly and I
wanted to check whether the difference we were seeing between the different
extraction methods was somehow a Velvet artefact.

The recent [GAGE-B paper](http://bioinformatics.oxfordjournals.org/content/ear
ly/2013/05/10/bioinformatics.btt273.abstract) showed that the
[SPAdes](http://bioinf.spbau.ru/spades/) assembler gave the best results at
100x coverage (N50 > 2x that of Velvet). SPAdes is a relatively new assembler,
originally intended for use with single cell sequencing data that also
performs well with standard data. It takes an interesting approach involving
the use of paired de Bruijn graphs which allow the integration of read-pair
info at a much earlier stage of assembly than most de Bruijn graph assemblers.
SPAdes recommends error correction prior to assembly,
[BayesHammer](http://www.biomedcentral.com/1471-2164/14/S1/S7), from the same
group in [St Petersburg](http://bioinf.spbau.ru/en), is bundled with SPAdes.
Quake is also recommended. As an aside, SPAdes was very straightforward to
install and run.

In addition to N50, assembly quality was assessed using
[REAPR](http://www.sanger.ac.uk/resources/software/reapr/), a reference free
tool from the Sanger. We had some teething issues getting this set up but the
developer, Martin Hunt, was helpful. REAPR assesses an assembly by mapping the
reads to the genome and looking at whether the paired information is congruent
with the assembly. It then breaks the assembly where it detects errors and
returns a corrected N50. For a few samples I compared the number of
misassemblies called with [Quast](http://bioinf.spbau.ru/quast), a reference
based assembly assessment tool we have used [in the
past](http://bitsandbugs.org/2013/05/02/velvet-optimiser-vs-kmer-genie/) and
REAPR.

So, what were the results?

\---------------------------------------------------------------------

Please continue to read [at his blog here](http://bitsandbugs.org/2013/06/28
/assembly-optimisation-impact-of-error-correction-and-a-new-assembler-
spades/).

