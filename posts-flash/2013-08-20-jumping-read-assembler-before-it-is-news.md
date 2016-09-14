---
title: Jumping Read Assembler - Before it is News
tags: []
categories:
- blog
---
The era of just-in-time science+'press release' entered a new phase, when
[news appeared before actual paper showed up](http://www.genomeweb.com/blog
/week-pnas-229) \-
<!--more-->

> In a study slated to appear in the early, online edition of the Proceedings
of the National Academy of Sciences, a Taiwan-led team introduces JR-
Assembler, a genome assembler named for the jumping extension and read
remapping that it uses to do de novo assembly of large genomes. In addition to
describing their assembler strategy and assessing its assembly statistics when
dealing with sequences from various species, the researchers used simulated
data to look at the computer memory use and processing time of the assembler,
which relies on so-called extension-based graphs rather than de Bruijn graphs.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture40-300x143.png)

What next? GenomeWeb retraction? :) Posting papers at arxiv can help in such
embarrassing situations. Thanks to a helpful reader, we located the software
and relevant webpage. Please click on the image below to get there.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture42-300x74.png)

Also, as an added service to our readers, we [presented the functions in their
code in our wiki page](http://homolog.us/wiki1/index.php?title=JR). If you
want to figure out how the code work, the wiki page may be handy.

Reader @chienchilo pointed out a poster from the same group, from which we now
know the names of the authors too !! This is the best we can do today, unless
Anonymous (or NSA) hacks into PNAS computers to send us a copy of the paper.

[JR-Assembler: a large-scale de novo assembly of short read sequences by
jumping extension and read remapping

Chu T*, Liu T, Lu C, Lee GC, Li W, Shih AC*Institute of Information Science,
Academia Sinica Taiwan

> De novo genome assembly using short read sequences is a highly challenging
problem. The major challenge for the de Bruijn graph-based assemblers is how
to reduce the graph complexity, so that the computer memory requirement will
not increase exponentially with the read length and, especially, the read
count. Here, we propose a new de novo assembly method, called JR-Assembler,
that can efficiently assemble a genome using hundreds of millions of Illumina
short read sequences with an efficient usage of computer memory. JR-Assembler
uses an advanced overlapping consensus approach that includes several
innovative ideas. It includes the following major steps: (a) seed selection,
in which both the frequency and overlapping information of reads are used to
select a set of reads for extension, (b) contig extension by jumping between
reads rather than base by base, (c) quality evaluation of extended sequences
by remapping unassembled reads at each extension and filtering out incorrect
extensions, (d) improvement of read connection by dynamically trimming low
quality nucleotides from the 3'-end of a read during extension, (e) repeat
identification by breaking the extension at each repeat boundary to reduce the
mis-assembly, and (f) merging multi-scale contigs by unassembled reads.
Empirical and simulation studies revealed that JR-Assembler achieves not only
better contig quality but also better memory usage than many popular methods,
such as Velvet and SOAPdenovo. Indeed, for a computer with 256GB RAM, only JR-
Assembler can handle several Giga reads within a reasonable time.

\-----------------------------------

Update: 9/22/2013

The paper is now available from PNAS website, provided you pay (h/t:
@SahaSurya). We also got a [link to their new website](http://jr-
assembler.iis.sinica.edu.tw/).

[Assembler for de novo assembly of large genomes](http://www.pnas.org/content/
early/2013/08/21/1314090110.short?rss=1&utm_source=buffer&utm_campaign=Buffer&
utm_content=buffer7a473&utm_medium=twitter)

> Assembling a large genome faces three challenges: assembly quality, computer
memory requirement, and execution time. Our developed assembler, JR-Assembler,
uses (a) a strategy that selects good seeds for contig construction, (b) an
extension strategy that uses whole sequencing reads to increase the chance to
jump over repeats and to expedite extension, and (c) detecting misassemblies
by remapping reads to assembled sequences. Compared with current assemblers,
JR-Assembler achieves a better overall assembly quality, requires less
execution time and requires, with one exception, less memory. The advantages
of JR-Assembler in memory usage and execution time will increase slowly as the
read length increases. Thus, contrary to the prevailing view, the extension
approach seems superior to the de Bruijn graph approach.

