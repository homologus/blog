---
title: Assemblathon, GAGE and Four Dimension of Evaluating Genome Assembly Programs
tags: []
categories:
- blog
---
We wrote about the Assemblathon paper in January, when it was first uploaded
in arxiv ([a place declared as 'low grade journal' by omniscient Andrew
Gilman](http://www.homolog.us/blogs/students/2013/07/11/andrew-gelman-angers-
readers-by-calling-plos-one-and-arxiv-low-grade-journals/)).
<!--more-->

[Notes on Assemblathon Paper](http://www.homolog.us/blogs/blog/2013/01/25
/notes-on-assemblathon-paper/)

[Titus Browns Thoughts on the Assemblathon 2
paper](http://www.homolog.us/blogs/blog/2013/02/23/titus-browns-thoughts-on-
the-assemblathon-2-paper/)

Based on tweets from @assemblathon, the paper will be out in 'print' soon.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture9-300x57.png)

\------------------------------------------------

Speaking of comparison between assembly programs, our reader Anton
Korobeynikov [emailed us a commentary that the readers will find
informative](http://bioinf.spbau.ru/en/content/spades-25-gage-b-data-sets).

>

The recently published GAGE-B paper (Magoc, et al., 2013) presents an
evaluation of several popular assemblers, including SPAdes 2.3.

Since SPAdes 2.5 is out, we evaluated it on the data sets from the GAGE-B
study. Four MiSeq data sets (B. cereus, R. sphaeroides, M. abscessus, and V.
cholerae) were selected for the assessment. Since these reads are 250 bp
length, we applied our recommendations for assembling long Illumina paired-end
reads with SPAdes.

The original coverage of those data sets is about 500x. However, in the GAGE-B
experiments, all data was down-sampled to 100x coverage, because higher
coverage barely affected contig size. Meanwhile, SPAdes benefits from high
coverage, so we decided to assemble the data sets with the original ~500x
coverage. Our tables contain the GAGE-B assemblies of 100x-coverage data, and
the SPAdes 2.5 assembly of 500x-coverage data.

The B. cereus data was downloaded from the official Illumina website. The
other three data sets were obtained from the Sequence Read Archive at NIHs
National Center for Biotechnology Information (NCBI): SRR522246 (R.
sphaeroides), SRR768269 (M. abscessus), SRR769320 (V. cholerae). Genome
references and contigs produced by other assemblers mentioned in the GAGE-B
study were downloaded from the GAGE-B website.

It includes a table of comparison between [various genome assembly
algorithms](http://bioinf.spbau.ru/en/content/spades-25-gage-b-data-sets) done
in the GAGE-B style. The numbers for SPADES improved a lot compared to what
was seen in GAGE-B paper.

[SPAdes and MaSuRCA Assemblers Performed Best in GAGE-B
Evaluation](http://www.homolog.us/blogs/blog/2013/05/20/spades-and-masurca-
assemblers-performed-best-in-gage-b-evaluation/)

Those seeking information on Ray and few other assemblers not included in the
above GAGE-B related link should check [here](http://bioinf.spbau.ru/spades).

\---------------------------------------------------

That brings us to the question of what Assemblathon-3 (or GAGE-C) should be
like. The comparisons are very informative for the community, but it would be
great, if three issues are addressed.

**Four Dimensions of Evaluating Genome Assembly Programs**

Users of bioinformatics programs care about three issues -

(i) Quality of results,

(ii) Time taken to get the answer,

(iii) Cost of analysis.

We split time and cost as separate metrics, because it is not possible to run
some assembly programs without 256 Gb or 512 Gb RAM, no matter how long you
are willing to wait. Assemblathon focused on the quality issue, but the other
two factors are quite important.

iv) Fourth dimension - polymorphic genomes

In trying to understand the genome assembly programs, we used to focus on
those three dimensions (quality, time, cost), until we came across the pacific
oyster genome. You can see how different the oyster genome is from others in
the [preqc charts of Jared
Simpson](https://dl.dropboxusercontent.com/u/8813551/preqc_report.pdf).

[Very Helpful Preprocessing Module for Those Interested in Assembling
Genomes](http://www.homolog.us/blogs/blog/2013/07/02/cool-preprocessing-model-
for-genome-assembly/)

Even excluding the other complexities such as metagenome, transcriptome or
single cell assembly, a comparison of assemblers need to address those four
dimensions to be fully informative.

**Rapidly changing nature of field**

Between the time the Assemblathon entries were submitted and the paper will be
formally published, many assembly algorithms changed a lot. To be useful to
the community, evaluations will possibly have to publish a lot in arxiv and
leave the 'high-grade' journals to Andrew Gelmans. In that way, SPAdes blog
has been very helpful, because they continually update their benchmarks with
the latest versions of other assemblers. For alignment programs, nothing is as
informative as the often updated [ROC curves from Heng Li's
website](http://lh3lh3.users.sourceforge.net/alnROC.shtml). The BWA-MEM paper
also includes information on run time for the programs.

![](http://lh3lh3.users.sourceforge.net/images/100se-10.png)

