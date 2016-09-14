---
title: SPAdes and MaSuRCA Assemblers Performed Best in GAGE-B Evaluation
tags: []
categories:
- blog
---
GAGE-B, run by Steven Salzberg's group, compared the performances of various
genome assembly programs. Its main difference with [Assemblathon
2](http://www.homolog.us/blogs/blog/2013/01/25/notes-on-assemblathon-paper/)
was that the evaluations were done on bacterial NGS libraries only, whereas
Assemblathon 2 focused on vertebrates. Salzberg group previously compared the
performances of large genome assemblies under GAGE evaluation.
<!--more-->

GAGE-B, unlike Assemblathon, was not conducted as a competition. Instead
Salzberg group installed the assembly programs themselves and ran them on
twelve different NGS libraries - _Rhodobacter sphaeroides (HiSeq 100bp),
Mycobacterium abscessus (HiSeq 100bp), Vibrio cholerae (HiSeq 100bp), Bacillus
cereus (HiSeq 100b[), Rhodobacter sphaeroides (MiSeq 250bp), Mycobacterium
abscessus (MiSeq 250bp), Vibrio cholerae (MiSeq 250bp), Aeromonas hydrophila
(MiSeq 250bp), Bacillus cereus, Bacteroides fragilis, Staph. aureus and
Xanthomonas axonopodis_. [The entire paper](http://bioinformatics.oxfordjourna
ls.org/content/early/2013/05/10/bioinformatics.btt273.full.pdf) is a must read
for anyone working on genome assembly, but if one statement stood out, it was
the following one from the fourth paragraph of discussion section.

**Overall MaSuRCA and SPAdes produced the best assemblies across these twelve bacterial organisms.**

We do not know why he statement did not make to the abstract. Was it because
the comparative results were not supportive of such a strong statement in
abstract, or was it to make sure other authors of genome assembly programs
were not offended? Here are our naive observations based on two comparison
tables.

**Allpaths-LG, Ray, Minia**

Allpaths-LG was not included in the comparison, because -

> Allpaths-LG explicitly requires a minimum of two libraries (a short library
and a jumping library), which means it could not be run on the data used in
this study).

Also Ray and Minia+scaffolder were not included.

**SGA**

Based on N50 measure ([an imperfect way to compare
assemblies](http://www.homolog.us/blogs/blog/2012/06/26/what-is-wrong-with-n50
-how-can-we-make-it-better-part-ii/)), SGA did not match the performances of
other assemblers in almost all of the bacterial data sets. That came as a big
surprise to us, because SGA was clearly the best assembler for at least one
Assemblathon 2 set and among the best for the other two Assemblathon 2 sets.
Is the difference due to not including Phusion along with SGA for GAGE-B? We
asked [Jared Simpson](https://twitter.com/jaredtsimpson) about whether GAGE-B
ran his program correctly and what the implication of GAGE-B results are. His
explanation would be helpful to readers to understand results for other
assemblers as well.

>

I think GAGE-B is a fair comparison and they spent time to explore the
parameters of SGA. I will give a few guesses as to why the performance was
lower than other assemblers:

1) Since SGA is designed for larger genomes, it does not use read pairs until
quite late in the assembly. With smaller genomes there is an opportunity to
introduce pairs earlier since the time and memory constraints are lower. Pairs
could be used to clean errors from the graph and resolve some repeats.

2) I have not tested SGA on 250bp reads. If a long read cannot be completely
corrected, it will be discarded by the error corrector. The corrector should
take more care and trim the ends of reads that cannot be completely corrected.

3) In general the algorithms are conservative (correctly pointed out in the
paper) to avoid misassemblies on repetitive genomes. With bacteria maybe the
algorithms are stricter than necessary. This includes both the error
correction and contig assembly steps.

These are just guesses though, I will have to download the data and look at
the results in detail to see where the best areas of improvement are.

**ABySS, CABOG, MIRA, Velvet**

Those four assemblers were usually better than SGA, but far worse than the
assembly with the best N50 in each of twelve test libraries.

**SOAPdenovo**

In half of the cases, SOAPdenovo produced assemblies with better N50 than the
above five assemblers (and sometimes the best), and in remaining half, it was
worst. That inconsistency is very puzzling.

**SPAdes and MaSuRCA**

Either SPAdes or MaSuRCA ranked as the top assembler in all evaluations.
Quoting GAGE-B paper:

> Although no assembler won on all the various metrics, the MaSuRCA assembler
had the largest contig sizes, measured by either N50 or corrected N50 values,
for ten of the twelve experiments. The SPAdes assembler, a relatively recent
entry into the next generation assembly field, came in first or essentially
tied for first for four of the twelve genomes. These results were consistent
across both 100bp (HiSeq) and 250bp (MiSeq) reads, although SPAdes had a
larger boost in improvement for the longer reads.

The paper has lot more interesting information and we have not looked at the
supplement yet.

