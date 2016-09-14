---
title: SOAPdenovo-Trans Paper Shows the Complexity of Transcriptome Assembly
tags: []
categories:
- rnaseq
---
[SOAPdenovo-Trans: De novo Transcriptome Assembly with Short RNA-Seq
Reads](http://arxiv.org/ftp/arxiv/papers/1305/1305.6760.pdf)
<!--more-->

The paper has many comparisons with Trinity and Oases. We [wrote a lot about
those two transcriptome assemblers](http://www.homolog.us/blogs/blog/category
/transcriptome-assembly/) two years back. It is unfortunate that Daniel
Zerbino was forced to stop developing Oases further, because the assembler was
pretty good except for its humongous memory needs.

Getting back to SOAPdenovo-Trans, those looking for ideas for future
development should jump straight to discussion section.

> Sequence assembly on real world datasets has always required a lot of minor
algorithmic developments to produce the best results. There is no one magic
idea that solves all of the problems. In this spirit, SOAPdenovo-Trans
combined insights from both Trinity and Oases, merged them with ideas
developed for the genome version of SOAPdenovo2, and then added a few insights
of our own, to produce an algorithm that is demonstrably superior to the
previous. This however is unlikely to be the last word in transcriptome
assembly. We tried one of the reference-based assemblers, Cufflinks, and
recovered even more full-length transcripts than SOAPdenovo-Trans. It is
unclear just how much of this improvement can be replicated without recourse
to a reference genome, but the results suggest that there is information in
these datasets that, perhaps, with the right algorithm can be recovered.

For example, a multiple k-mers strategy may improve transcriptome assembly.
Current multiple k-mers assembly strategies generally fall into one of two
tags: []
categories: (a) After running different values of k-mer assembly separately,
merge these assemblies into one final set. This strategy may construct a more
complete transcript set but may also introduce redundancy. (b) Iterate
different k-mer de Bruijn graph assemblies during contig construction. This
strategy potentially makes the best use of reads and paired-end information.
Whether or not it is worth the effort to develop such algorithms depends in
part on continuing progress in sequencing technology, since if the promised
improvements in read lengths materialize, the nature of the problem will
change radically.

Related Seqanswers threads -

1\. [Knowledge about SOAPdenovo-
trans](http://seqanswers.com/forums/showthread.php?t=17959)

The comment by dongilbert is helpful.

> Find here a summary of my uses of your RNA transcript assemblers, comparing
with what I see as 3 good and improving programs for this: Velvet/Oases,
Trinity and SOAPdenovo-Trans.

http://arthropods.eugenes.org/EvidentialGene/evigene/evigene_rnaseq_2012_stats
.txt

Very briefly, three de-novo assemblers tested here are closely ranked, and
ranking depends on the particular species and data set used.

Locust insect: Velvet/O > Trinity > SOAPTrans

Cacao plant: SOAPTrans > Trinity > Velvet/O >> Cufflinks

Daphnia waterflea: Velvet/O > SOAPTrans > Trinity >> Cufflinks

SOAPTrans in particular can assembly better, quicker, with less memory use
than the other two. It can also fail inexplicably, or do worse than the
others.

My recommendation is to try these three, see which works for you and if
possible use them all and extract the best subset by some gene evidence
criteria (like homology, high coding ratio, ...).

2\. [SOAPdenovo-Trans: Seg
fault](http://seqanswers.com/forums/showthread.php?t=20598)

Many people reported odd behavior (i.e. failing inexplicably, as mentioned by
dongilbert).

3\. [SOAPdenovo-trans alternative
splicing](http://seqanswers.com/forums/showthread.php?t=21995)

> While Oases found massive sequences that have possible alternative splice
products, SOAPdenovo-trans did not find a single one. I used 12 different
k-mers from 19 to 89, e 1,3,5 and d 1,3,5 with all combinations. I allowed up
to 10 alternative splicing products.

