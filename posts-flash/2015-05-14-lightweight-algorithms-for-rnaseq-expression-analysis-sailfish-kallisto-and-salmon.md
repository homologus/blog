---
title: Lightweight Algorithms for RNAseq Expression Analysis - Sailfish, Kallisto
  and Salmon
tags: []
categories:
- blog
---
The world of RNAseq expression analysis has a number of exciting developments.
We have been covering them in [our RNAseq
blog](http://www.homolog.us/blogs/rnaseq/), but thought a summary in this
bioinformatics blog would be helpful to our readers.
<!--more-->

**The Problem**

RSEM, the commonly used program for RNAseq expression analysis, runs very
slowly. I know of one postdoc, who started her RNAseq analysis just prior to
the birth of her son Samuel. By the time that RSEM run finished, Samuel
finished his PhD and started his postdoc project to run, guess what, RSEM !!
Another person hand-counted (with help from beads and abacus) his entire
RNAseq library consisting of fifty HIseq files, and still finished before
RSEM.

Jokes apart, RSEM is slow and, more importantly, makes researchers dependent
on core facilities, cloud vendors, multi-core servers and the most expensive
of all - graduate students :). Thankfully the liberating alternatives are
[here](http://www.homolog.us/blogs/rnaseq/2015/05/11/pachter-blogs-on-
sailfish-vs-kallisto/).

> As someone who has worked on RNA-Seq since the time of 32bp reads, I have to
say that kallisto has personally been extremely liberating. It offers freedom
from the bioinformatics core facility, freedom from the cloud, freedom from
the multi-core server, and in my case freedom from my graduate students for
the first time in years Im analyzing tons of data on my own; because of the
simplicity and speed I find I have the time for it. Enjoy!

**Sailfish**

Sailfish is included in Pandora's Toolbox for Bioinformatics for being a very
efficient ('lightweight') program for expression analysis. [This
code](http://arxiv.org/abs/1308.3700) developed by Rob Patro and collaborators
truly saved our life, and we wrote about the paper and code several times
including '([Goodbye RSEM, Sailfish Paper
Published](http://www.homolog.us/blogs/rnaseq/2014/04/21/goodbye-rsem-
sailfish-paper-published/))'.

In terms of algorithm, sailfish uses kmer counting to parse the reads into
kmers and compares with the reference library stored as perfect hash.

**Kallisto**

[Kallisto](http://www.homolog.us/blogs/rnaseq/2015/05/06/kallisto-from-
pachterlab-for-rnaseq-quantification/), developed by Pachter lab, uses similar
lightweight approach and [improves on
sailfish](http://www.homolog.us/blogs/rnaseq/2015/05/11/pachter-blogs-on-
sailfish-vs-kallisto/). Pll Melsted, whose bioinformatics research has been
featured in our blog many times, played a big role in developing the computer
code. [Pachter's blog post](http://www.homolog.us/blogs/rnaseq/2015/05/11
/pachter-blogs-on-sailfish-vs-kallisto/) described Kallisto -

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

**Salmon**

In the meanwhile, Rob Patro, the developer of Sailfish, is not sitting still
and has been busy doing a lot of 'fishy' things. He brought another fish
Salmon to the RNAseq shop. Here is his latest blog post -

[Not-quite alignments: Salmon, Kallisto and Efficient Quantification of RNA-
Seq data](http://robpatro.com/blog/?p=248)

> **Kallisto**

Nick Bray, Harold Pimentel, Pll Melsted and Lior Pachter introduced a new
method and tool, called kallisto for fast and accurate quantification of
transcript-level abundance from RNA-seq data. I had a chance to drop by the
poster session and speak with the first 3 authors, and also (in the last hour)
to read the pre-print of the paper. First, I should say that I think the idea
behind kallisto and the implementation of the software are excellent (Liors
group has a history of developing very cool methods and backing these up with
well-written, well-maintained software). Basically, they demonstrate that you
can obtain the speed of a tool like Sailfish (which quantifies abundance based
on k-mers and k-mer counts) without shredding the reads into k-mers, which can
sometimes discard useful information contained therein. Along with an
efficient implementation and (from what I can see so far, some very nice C++11
source code), these results are obtained mainly through the concept of
pseudoalignments.

Essentially, pseudoalignments define a relationship between a read and a set
of compatible transcripts (this relationship is computed based on mapping the
k-mers to paths in a transcript De Bruijn graph). The pseudoalignment here
gives us more information than the set of individual k-mers, since the k-mers
in a read remain coupled when the read is assigned to a transcript equivalence
class. As the pseudoalignments are generated, equivalence classes are computed
and maintained similar to the concept of equivalence classes among reads as
introduced in the IsoEM paper or to equivalence classes among k-mers as used
in Sailfish.

The results of kallisto are very impressive, and the idea of pseudoalignments,
is, I think, a very good one (more on this below). Essentially, we are
converging upon an answer to the question, what information is really needed
to obtain accurate quantification estimates?, and trying to develop methods
that use this information to compute answers as efficiently as possible (but
no more efficiently ;P).

**Salmon**

One of the reasons kallisto and its ideas are so close to my heart is that,
after the publication of Sailfish, Carl and I didnt stop thinking about where
the Sailfish model might fall short and how it might be improved. In a
somewhat awesome twist of fate, while the kallisto team was in some sense
inspired (or at least provoked to deep thought) by the approach of Sailfish,
we were also inspired by some of the ideas introduced in Liors (and his
previous student Adam Roberts) prior RNA-seq quantification tool, eXpress.

**Pandora's Toolbox for Bioinformatics**

In the [Pandora's Toolbox for
Bioinformatics](http://www.homolog.us/blogs/blog/2015/04/21/free-ebook-
pandoras-toolbox-for-bioinformatics/), we already included the Salmon version
of Sailfish. As soon as I get time, I will include the Kallisto code and
algorithm in the free book and [the corresponding github
code](https://github.com/homologus/Pandoras-Toolbox-for-Bioinformatics). The
main goal here is to create a single download point for a small number of
important and efficient bioinformatics programs so that an user can get
started quickly.

**Stay away from digital normalization**

If you are a bioinformatics technician, who uses digital normalization several
times on every data set without thinking much, the following blog post of
Pachter and the related discussions would be useful.

[Digital normalization revealed](https://liorpachter.wordpress.com/2014/09/11
/digital-normalization-revealed/)

> It turns out that Tic Tacs are in fact almost pure sugar. Its easy to figure
this out by looking at the number of calories per serving (1.9) and
multiplying the number of calories per gram of sugar (3.8) by 0.49 => 1.862
calories. 98% sugar! Ferrero basically admits this in their FAQ. Acting
completely within the bounds of the law, they have simply exploited an
arbitrary threshold of the FDA. Arbitrary thresholds are always problematic;
not only can they have unintended consequences, but they can be manipulated to
engineer desired outcomes. In computational biology they have become
ubiquitous, frequently being described as filters or pre-processing steps.
Regardless of how they are justified, thresholds are thresholds are
thresholds. They can sometimes be beneficial, but they are dangerous when
wielded indiscriminately.

There is one type of thresholding/filtering in used in RNA-Seq that my postdoc
Bo Li and I have been thinking about a bit this year. It consists of removing
duplicate reads, i.e. reads that map to the same position in a transcriptome.
The motivation behind such filtering is to reduce or eliminate amplification
bias, and it is based on the intuition that it is unlikely that lightning
strikes the same spot multiple times. That is, it is improbable that many
reads would map to the exact same location assuming a model for sequencing
that posits selecting fragments from transcripts uniformly. The idea is also
called de-duplication or digital normalization.

Digital normalization is obviously problematic for high abundance transcripts.
Consider, for example, a transcripts that is so abundant that it is extremely
likely that at least one read will start at every site (ignoring the ends,
which for the purposes of the thought experiment are not relevant). This would
also be the case if the transcript was twice as abundant, and so digital
normalization would prevent the possibility for estimating the difference.
This issue was noted in a paper published earlier this year by Zhou et al. The
authors investigate in some detail the implications of this problem, and
quantify the bias it introduces in a number of data sets. But a key question
not answered in the paper is what does digital normalization actually do?

