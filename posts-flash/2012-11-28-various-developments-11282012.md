---
title: Various Developments - 11&#47;28&#47;2012
tags: []
categories:
- blog
---
1\. [Generation of Artificial FASTQ Files to Evaluate the Performance of Next-
Generation Sequencing Pipelines](http://www.plosone.org/article/info%3Adoi%2F1
0.1371%2Fjournal.pone.0049110) (hat tip @genetics_blog)
<!--more-->

> We have developed ArtificialFastqGenerator, which takes a reference genome
sequence as input and outputs artificial paired-end FASTQ files containing
Phred quality scores. Since these artificial FASTQs are derived from the
reference genome, it provides a gold-standard for read-alignment and variant-
calling, thereby enabling the performance of any NGS pipeline to be evaluated.
The user can customise DNA template/read length, the modelling of coverage
based on GC content, whether to use real Phred base quality scores taken from
existing FASTQ files, and whether to simulate sequencing errors. Detailed
coverage and error summary statistics are outputted.

Download code [here](http://sourceforge.net/projects/artfastqgen/)

2\. [RNA-seq and microarray complement each other in transcriptome
profiling](http://www.ncbi.nlm.nih.gov/pubmed/23153100)

> We compared the performance of RNA-seq and microarray in their ability to
detect known HrpX target genes by profiling the transcriptome from the wild-
type and the hrpX mutant strains of gamma-Proteobacterium Xanthomonas citri
subsp. citri.

...

Finally, in addition to the 55 newly identified DEGs, 72% of the already known
HrpX target genes were detected by both RNA-seq and microarray, while, the
remaining 28% could only be detected by either one of the methods.

....

RNA-seq and microarray together provide a more comprehensive picture of HrpX
regulome by uniquely identifying new DEGs. Our study demonstrated that RNA-seq
and microarray complement each other in transcriptome profiling.

3\. [DiffSplice: the genome-wide detection of differential splicing events
with RNA-
seq](http://nar.oxfordjournals.org/content/early/2012/11/15/nar.gks1026.long)
(h/t @genetics_blog)

Did not Rayan Chikhi's collaborators publish a [similar
paper](http://www.biomedcentral.com/1471-2105/13/S6/S5) few months back?

Another related paper came out recently - [Intron-Centric Estimation of
Alternative Splicing from RNA-seq data](http://bioinformatics.oxfordjournals.o
rg/content/early/2012/11/21/bioinformatics.bts678.long) by Dmitri D.
Pervouchine et al.

4\. [Nvidia says large GPGPU speed up claims were due to bad original
code](http://m.theinquirer.net/inquirer/news/2227038/nvidia-says-large-gpgpu-
speed-up-claims-were-due-to-bad-original-code#.ULOMfesxUW0.twitter)

> CHIP DESIGNER Nvidia has said that most of the outlandish performance
increase figures touted by GPGPU vendors was down to poor original code rather
than sheer brute force computing power provided by GPUs.

Both AMD and Nvidia have been using real-world code examples and projects to
promote the performance of their respective GPGPU accelerators for years, but
now it seems some of the eye popping figures including speed ups of 100x or
200x were not down to just the computing power of GPGPUs. Sumit Gupta, GM of
Nvidia's Tesla business told The INQUIRER that such figures were generally
down to starting with unoptimised CPU code.

........

Gupta said, "Most of the time when you saw the 100x, 200x and larger numbers
those came from universities. Nvidia may have taken university work and shown
it and it has an 100x on it, but really most of those gains came from academic
work. Typically we find when you investigate why someone got 100x [speed up]
is because they didn't have good CPU code to begin with. When you investigate
why they didn't have good CPU code you find that typically they are domain
scienctists not computer science guys - biologists, chemists, physics - and
they wrote some C code and it wasn't good on the CPU.

...........

According to Gupta, those users that have optimised their code to squeeze most
of the performance out of the CPU can get somewhat more sedate performance
gains. "Most people we find who have optimised CPU code, and really you'll
only find optimised CPU code in the HPC world, get between 5x to 10x speed up,
that's the average speed up that people get. In some cases it's even less,
we've seen people getting speed ups of 2X but they are delighted with 2x
because there is no way for them to get a sustainable 2X speed up from where
they are today," said Gupta.

5\. [Posting Blog Entries to Figshare](http://ivory.idyll.org/blog/posting-
blog-entries-to-figshare.html#comment-719269763)

The guy from ivory basement is at it again. He figured out how to give DOI IDs
to blog entries and get them counted as citations.

Next problem for him - figure out how to retract blog publications :)

Also check [this blog post](http://www.carlboettiger.info/2012/11/23/citing-
lab-notebook-entries.html) on related topic.

6\. And the greatest news of the day - [gmail will allow attachments of size
up to 10 GB](http://gmailblog.blogspot.com/2012/11/gmail-and-drive-new-way-to-
send-files.html).

