---
title: Pachter Blogs on Sailfish vs Kallisto
categories:
- rnaseq
---
[This blog post](https://liorpachter.wordpress.com/2015/05/10/near-optimal-
rna-seq-quantification-with-kallisto/) is a must-read !
<!--more-->

> The project began in August 2013 when I wrote my second blog post, about
another arXiv preprint describing a program for RNA-Seq quantification called
Sailfish (now a published paper). At the time, a few students and postdocs in
my group read the paper and then discussed it in our weekly journal club. It
advocated a philosophy of lightweight algorithms, which make frugal use of
data, respect constant factors and effectively use concurrent hardware by
working with small units of data where possible. Indeed, two themes emerged in
the journal club discussion:

1\. Sailfish was much faster than other methods by virtue of being simpler.

2\. The simplicity was to replace approximate alignment of reads with exact
alignment of k-mers. When reads are shredded into their constituent k-mer
mini-reads, the difficult read -> reference alignment problem in the presence
of errors becomes an exact matching problem efficiently solvable with a hash
table.

We felt that the shredding of reads must lead to reduced accuracy, and we
quickly checked and found that to be the case. In fact, in our simulations, we
saw that Sailfish significantly underperformed methods such as RSEM. However
the fact that simpler was so much faster led us to wonder whether the
prevailing wisdom of seeking to improve RNA-Seq analysis by looking at
increasingly complex models was ill-founded. Perhaps simpler could be not only
fast, but also accurate, or at least close enough to best-in-class for
practical purposes.

After thinking about the problem carefully, my (now former) student Nicolas
Bray realized that the key is to abandon the idea that alignments are
necessary for RNA-Seq quantification. Even Sailfish makes use of alignments
(of k-mers rather than reads, but alignments nonetheless). In fact, thinking
about all the tools available, Nick realized that every RNA-Seq analysis
program was being developed in the context of a pipeline of first aligning
reads or parts of them to a reference genome or transcriptome. Nick had the
insight to ask: what can be gained if we let go of that paradigm?

By April 2014 we had formalized the notion of pseudoalignment and Nick had
written, in Python, a prototype of a pseudoaligner. He called the program
kallisto. The basic idea was to determine, for each read, not where in each
transcript it aligns, but rather which transcripts it is compatible with. That
is asking for a lot less, and as it turns out, pseudoalignment can be much
faster than alignment. At the same time, the information in pseudoalignments
is enough to quantify abundances using a simple model for RNA-Seq, a point
made in the isoEM paper, and an idea that Sailfish made use of as well.

Just how fast is pseudoalignment? In January of this year Pll Melsted from the
University of Iceland came to visit my group for a semester sabbatical. Pll
had experience in exactly the kinds of computer science we needed to optimize
kallisto; he has written about efficient k-mer counting using the bloom filter
and de Bruijn graph construction. He translated the Python kallisto to C++,
incorporating numerous clever optimizations and a few new ideas along the way.
His work was done in collaboration with my student Harold Pimentel, Nick (now
a postdoc with Jacob Corn and Jennifer Doudna at the Innovative Genomics
Initiative) and myself.

And finally -

> **As someone who has worked on RNA-Seq since the time of 32bp reads, I have
to say that kallisto has personally been extremely liberating. It offers
freedom from the bioinformatics core facility, freedom from the cloud, freedom
from the multi-core server, and in my case freedom from my graduate students
for the first time in years Im analyzing tons of data on my own; because of
the simplicity and speed I find I have the time for it. Enjoy!**

