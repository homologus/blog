---
title: Bioinformatics at a Crossroad Again - Which Way Next?
tags: []
categories:
- blog
---
![crossroad](http://www.homolog.us/blogs/wp-content/uploads/2014/08/crossroad-
243x300.jpg)
<!--more-->

One of our readers asked - "If genome assembly becomes a solved problem,
what's next?"

We like to broaden the comment to argue that the entire field of
bioinformatics is again at a turning point, because almost all difficult
computational problems related to 'next-generation sequencing' have been
solved satisfactorily. Readers are encouraged to express their differing
opinions in the comment section.

Let us first briefly mention three different phases the field of
bioinformatics went through. In the first era (prior to 1999), bioinformatics
was an obscure field with very few talented and die-hard practitioners, who
preferred to call themselves mathematicians or computer scientists. The second
era (1999-2008) was rather frustrating for those skilled practitioners,
because NIH showered huge amount of money on all kinds of biologists, who were
more eager to find someone manage their microarray databases and Excel
spreadsheets than those working on elegant algorithms. Good computational
papers written in this era got very few citations compared to database papers.

The dam broke with the advent of short-read sequencing, because it was no
longer possible to analyze data in an Excel sheet. Moreover, a bigger problem
emerged. It was not even clear whether the short reads (or noisy long Pacbio
reads) were useful for anything, and computer scientists had to be brought
back for rescue. They first showed that the short (and noisy long) reads were
indeed useful, but only if new classes of algorithms were developed.
Additionally, a substantial investment in expensive servers was needed. For
example, PacBio reported assembling the human genome from PacBio reads in
400,000 'Google exascale CPU hours', where alignment between reads took most
of the time. In another example of hardware cost, servers with 512GB to 1TB
RAM were often used to assemble human genome or other large genomes.

More recent developments suggest that the second criterion will not be
critical going forward. This has been achieved through use of clever
algorithms or non-Intel hardware. For example, Gene Myers brought down the
alignment time of PacBio reads by 25-fold based on [his new DALIGN
algorithm](http://www.homolog.us/blogs/blog/2014/07/28/in-dalign-paper-gene-
myers-delivers-a-major-blow-to-his-biggest-competitor/). [Tak-wah Lam's group
developed GPU-based algorithms](http://www.homolog.us/blogs/blog/2014/04/24
/balsa-integrated-secondary-analysis-for-whole-genome-and-whole-exome-
sequencing-accelerated-by-gpu/) to cut down the variant calling time
significantly compared to GATK. Rayan Chikhi and collaborators showed how to
do human genome assembly with only 1-2GB of RAM. Titus Brown developed
approximate algorithms to rapidly get to the results with hardly any loss of
information. [Sailfish](http://www.homolog.us/blogs/rnaseq/2014/04/21/goodbye-
rsem-sailfish-paper-published/) cut down the expression quantification time of
RNAseq data of RSEM from days to minutes.

Those are only a few examples, but if the trend continues (and we do not see
why not), it will soon be possible to do de novo assembly and analysis of
RNAseq data in real time, or assemble human genome from short or long reads in
less than an hour, or align 1 billion reads on to human genome in less than an
hour - all in inexpensive regular-RAM servers. Speaking of quality of
information, the short read noise is expected go away with proper
incorporation of long PacBio data.

If all difficult problems are handled satisfactorily, what will the
bioinformaticians do next? In the following few commentaries, we will provide
our best answer, but please feel free to suggest any difficult problem that
remains unsolved.

