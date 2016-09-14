---
title: Top Bioinformatics Contributions of 2012
tags: []
categories:
- blog
---
Dear readers, two weeks back we asked for your suggestions for [best
bioinformatics innovations of 2012](http://www.homolog.us/blogs/2012/12/28
/top-five-bioinformatics-innovations-of-2012-contest/). In addition to topics
covered in our blog over the entire year, we received several other good
suggestions by email and in the comment section. We also went through all 2012
issues of nine major journals, read the abstracts and shortlisted few more
papers that seemed interesting. Additionally, we checked all 2012 posts of
four [bioinformatics-related blogs we
follow](http://www.homolog.us/blogs/2012/07/27/how-to-stay-current-in-
bioinformaticsgenomics/) to make sure nothing is missed. We could not read
everything submitted to arxiv.org, but [Haldane's
Sieve](http://haldanessieve.org/) came to be of great help to reduce our load.
<!--more-->

That was lot of work, but then we faced the dilemma of how to judge between
topics as diverse as a very good alignment algorithm and an excellent
educational resource in bioinformatics. They solve problems so different that
it is nearly impossible to say which one is 'better'. Should we rank them all
by some metrics and pick top five, to end up in a situation, where all top
innovations were assembly algorithms? Or should we try to select one each from
various categories? We went for the later, but also decided to disclose the
tags: []
categories so that there is no confusion among our readers.

We will list our final results in five categories - (i) best blog/social
media+twitter feed, (ii) most innovative assembly algorithm, (iii) best
educational resource, (iv) best scientific contribution related to
bioinformatics and (v) best bioinformatics journal. For entertainment, we also
include the most over-rated scientific discovery of 2012 (thankfully happens
to be not bioinformatics-related).

Please feel free to discuss in the comment section, if you do not agree with
our choices or would like to suggest other interesting contributions missed by
us.

\---------------------------------------------------------------

**Best blog + Twitter feed - Getting Genetics Done + @genetics_blog **

![stephen-turner](http://www.homolog.us/blogs/wp-content/uploads/2013/01
/stephen-turner.jpg)

Blogging is a new platform for communication, and this method started to gain
traction among scientists over the last two years. Most online-savvy
researchers also maintain a Twitter feed to post other interesting information
that may or may not be worthy of a full blog post. Additionally, [online
forums like SeqAnswers](http://seqanswers.com/) have become invaluable tools
for bioinformatics researchers, because they bring many practitioners together
and allow them to share ideas. It is very difficult to rank various social
media channels, because all channels have their own whims and personalities.
Still, we decided to create a shortlist from [a number of excellent resources
listed here](http://www.homolog.us/blogs/2012/07/27/how-to-stay-current-in-
bioinformaticsgenomics/), and asked the question - which channel, if it goes
away, would be the one most missed by us? For bloggers also maintaining
Twitter feed, we combined the contributions in those two channels together.

Following blogs, Twitter feeds and social media channels were shortlisted (not
ranked in any order).

1\. [Openhelix](http://www.openhelix.com/), Twitter feed @OpenHelix

2\. [Haldane's Sieve](http://haldanessieve.org/)

3\. Titus Brown's blog [Living in an Ivory
Basement](http://ivory.idyll.org/blog) and Twitter Feed @ctitusbrown

4\. [Getting Genetics Done](http://gettinggeneticsdone.blogspot.com/) \+
@genetics_blog

5\. [SeqAnswers](http://seqanswers.com/) online forum.

6\. Jonathan Eisen's [The Tree of Life](http://phylogenomics.blogspot.com/)

All seemed of nearly equal importance to the community and to us. Still, we
felt that the daily update of important papers by @genetics_blog saved us tons
of time, and were the most invaluable resources.

\----------------------------------------------------------------

**Best Assembly Algorithm - Minia**

The focus of our blog was to cover various NGS-related assembly algorithms,
and therefore we decided to make it a different category. We shortlisted the
following innovations (not ranked in any order).

[Minia](http://www.homolog.us/blogs/2012/10/01/minia-assembly-algorithm-and-
french-revolution/)

[String Graph Assembler](http://www.homolog.us/blogs/2012/02/11/string-graph-
assembler/), also check [here](http://www.homolog.us/blogs/2012/02/13/string-
graph-of-a-genome/).

[Rectangular graph](http://www.homolog.us/blogs/2012/09/12/from-de-bruijn-
graphs-to-rectangle-graphs-for-genome-assembly/)

[Scaling metagenome assembly with probabilistic de Bruijn
graphs](http://www.homolog.us/blogs/2012/07/19/quip-minia-slimgene-and-titus-
browns-paper-on-scaling-metagenome/)

[Ray Meta: Scalable de Novo Metagenome Assembly and
Profiling](http://www.homolog.us/blogs/2012/12/27/ray-meta-scalable-de-novo-
metagenome-assembly-and-profiling/)

[Cortex Assembler](http://www.homolog.us/blogs/2012/12/12/exploring-single-
sample-snp-and-indel-calling-with-whole-genome-assembly/)

They were all so good and addressed such widely different aspects of genome
assembly that it was very difficult to compare them against each other. SGA
used a new graph technique to solve contig construction part of genome
assembly. Titus Brown's paper worked on data reduction, which was essential
for a large assembly. Cortex addressed haplotype difference issue, and
rectangular graphs were proposed to do scaffolding very elegantly.

We could not do proper justice to Ray Meta, because the paper came out very
late in the year and we did not have enough time to fully grasp all details
like we did with other ones.

We selected Minia for two reasons.

(i) Firstly, the algorithm proposed an elegant way to reduce redundancies in
de Bruijn graphs. When a de Bruijn graph is constructed, each k-mer has
extensive overlap with the consecutive k-mer, and longer the k-mer size is for
graph construction, more is the redundancy. Reducing the graph size and
therefore the needed RAM was a very important issue for handling very large
assembly problems, and Minia provides a method that leads to dramatic data
reduction without leading to any approximation in the assembly.

(ii) The optimal bits/k-mer analysis of NGS data (Fig. 2) presented in the
Minia paper was very interesting, and may be helpful for other papers working
on de Bruijn graphs.

Nevertheless, other assemblers mentioned above appear so innovative that we
constructed [wiki pages for each of
them](http://homolog.us/wiki1/index.php?title=Main_Page) to analyze and
understand the codes. The authors have been very generous in making their
codes open-source, and we should make every effort to make best use of that
opportunity, and not consider each bioinformatics program a 'package with
parameters and specifications'.

\---------------------------------------------------------------------

**Best Educational Resource - Rosalind**

We considered following alternatives -

[Rosalind](http://www.homolog.us/blogs/2012/09/18/rosalind-project-at-
algorithmic-biology-laboratory-st-petersburg/)

[Iphython Notebook](http://www.homolog.us/blogs/2012/10/21/ipython-notebook-
and-de-bruijn-graph/)

[Socraticqs](http://www.homolog.us/blogs/2012/11/02/on-teachinglearning-
bioinformatics-online-socraticqs-rosalind/)

[Software carpentry](http://www.homolog.us/blogs/2012/10/04/software-
carpentry-very-good-place-to-learn-scientific-programming/)

Rosalind beats them all hands down. The topic on Rosalind was also very
popular in Reddit.

\----------------------------------------------------------------------

**Best Scientific Contribution related to Bioinformatics**

A pair of papers published by Joanna I. Su?kowska _et al._ in June 2012 issue
of PNAS got our top vote.

[Conservation of complex knotting and slipknotting patterns in
proteins](http://www.pnas.org/content/109/26/E1715.full)

[Genomics-aided structure
prediction](http://www.pnas.org/content/109/26/10340.full)

The above decision will take more space to explain, and we will do that in a
subsequent commentary. Following papers or groups of papers were considered in
our final list.

1\. **BLASR paper**

[Mapping single molecule sequencing reads using Basic Local Alignment with
Successive Refinement (BLASR): Theory and Application - M.
Chaisson](http://www.biomedcentral.com/1471-2105/13/238/abstract)

2\. [A Classification of Bioinformatics Algorithms from the Viewpoint of
Maximizing Expected Accuracy (MEA) - Michiaki Hamada and Kiyoshi
Asai](http://online.liebertpub.com/doi/full/10.1089/cmb.2011.0197)

3\. [Ryan Urbanowicz et. al. The Role of Genetic Heterogeneity and Epistasis
in Bladder Cancer Susceptibility and Outcome: A Learning Classifier System
Approach"](http://www.snubi.org/TBC2012/presentation.htm#S8_2)

4\. **SPAdes paper trio**

Pathset Graphs: A Novel Approach for Comprehensive Utilization of Paired Reads
in Genome Assembly - Son K. Pham, Dmitry Antipov, Alexander Sirotkin, Glenn
Tesler, Pavel A. Pevzner, Max A. Alekseyev

SEQuel: improving the accuracy of genome assemblies - R. Ronen, C. Boucher, H.
Chitsaz, P. Pevzner, Bioinformatics. Jun 2012

Paired de Bruijn Graphs: A Novel Approach for Incorporating Mate Pair
Information into Genome Assemblers -Paul Medvedev, Son Pham, Mark Chaisson,
Glenn Tesler, Pavel Pevzner

5\. Protein Folding papers

[Conservation of complex knotting and slipknotting patterns in
proteins](http://www.pnas.org/content/109/26/E1715.full)

[Genomics-aided structure
prediction](http://www.pnas.org/content/109/26/10340.full)

6\. [The mystery of missing heritability: Genetic interactions create phantom
heritability - Or Zuk, Eliana Hechter, Shamil R. Sunyaeva and Eric S.
Lander.](http://www.pnas.org/content/early/2012/01/04/1119675109)

\-----------------------------------------------------------------------

**Best Bioinformatics Journal - J. Computational Biology**

[Journal of Computational Biology

Co-Editors-in-Chief: Sorin Istrail, PhD and Michael S. Waterman, PhD

We must admit that we started with a bias, and thought we could pick
'arxiv.org' as the most exciting up-and-coming bioinformatics journal. That
was in line with many of our earlier commentaries on open publication and
internet communication. The last thing we thought we would do was to pick a
closed journal.

Then we decided to compare our choice with various journals we check from time
to time, and the quality of unusual bioinformatics-related papers published
last year in J. Comp. Biol. blew our mind. They were far more thoughtful
articles than merely combining various computational techniques to develop
'tools' or 'databases'. We like to go through many of the published articles
as time permits, and discuss in our blog.

\-----------------------------------------------------------------------

**Most Over-rated Scientific Discovery - Discovery of Higgs Boson**

Discovery of Higgs boson and killing of Osama bin Laden were two stories over-
hyped by mainstream media in 2012, and they have many similarities.

1) They were both very expensive 'needle-in-a-haystack' operations.

2) Both events were deemed important in an earlier era, but the world changed
so much since then that their relative significances went down drastically.

[Here](http://www.homolog.us/blogs/2012/07/06/more-is-different/) were our
thoughts on discovery of Higgs boson, when the news was announced.

