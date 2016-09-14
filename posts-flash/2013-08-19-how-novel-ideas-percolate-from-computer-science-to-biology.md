---
title: How Novel Ideas Trickle Down from Computer Science to Biology
tags: []
categories:
- rnaseq
---
[The following linear narrative skips a few relevant citations.]
<!--more-->

![](http://cseweb.ucsd.edu/~ppevzner/images/pavel.jpg)

In 2001, Pavel Pevzner wrote an interesting paper titled -

[An Eulerian path approach to DNA fragment
assembly](http://www.pnas.org/content/98/17/9748.full)

The paper collected fourteen princely citations in seven years, excluding
those from the authors and their 'friends and families'.

\-------------------------------

Although the algorithm by Pevzner and colleagues was good, their program was
possibly not biologist-friendly (whatever that means). The 2008 program Velvet
implementing similar de Bruijn graph-based algorithm found wider use than
[2007 program EULER-SR by Chaisson and
Pevzner](http://genome.cshlp.org/content/18/2/324.full).

[Velvet: Algorithms for de novo short read assembly using de Bruijn
graphs](http://genome.cshlp.org/content/18/5/821.abstract)

\------------------------------

Although Velvet was excellent for bacterial assembly, it failed spectacularly
for human genome, just like the senior author of Velvet paper. BGI wrote a
fast and scalable program that found wider use.

[De novo assembly of human genomes with massively parallel short read
sequencing](http://genome.cshlp.org/content/20/2/265.long)

\------------------------------

SOAPdenovo was good for genome assembly, but not for transcriptomes. Trinity,
a de Bruijn graph-based assembler written by researchers from Broad Institute,
worked better for transcriptomes. Their paper was published in 2011.

[Full-length transcriptome assembly from RNA-Seq data without a reference
genome](http://www.nature.com/nbt/journal/v29/n7/abs/nbt.1883.html)

\-------------------------------

Fast forward to 2013, when a biology lab at Stanford presented the procedure
in 'biologist-friendly language' in their ['Simple Fools
Guide'](http://sfg.stanford.edu/). The pdf guide is available from
[here](http://sfg.stanford.edu/SFG.pdf). De novo assembly, the most difficult
step in the RNAseq pipeline, is explained in the following biologist-friendly
text.

> Buildingade novoassemblyisaverymemory-intensive process.Therearemanyprograms
forthis,someofwhicharelistedintheResourcessectionofthischapter.Inourexperience
,theonethatcanbeusedmosteffectivelyonanyfairlynewMaccomputerisCLCgenomicsworkb
ench,asmostothersrequiremoreRAMmemorythantypicallyisavailableonpersonalcompute
rs(inthe100sofGB,dependingonthenumberofreads).CLCistheonlysoftwareinthisprotoc
olthatisnotopensource(anacademiclicenseiscurrently$4,995
),althoughthereisafreetwo-week
trialversionavailable.Unliketheothersoftwareinthisprotocol,CLChasapoint?and-cl
ickgraphicaluserinterfaceandisveryeasytouse.CLCusesDeBruijngraphstojoinreadsto
gether.

\----------------------------------

If after reading the above narrative, you still have not figured out why Pavel
Pevzner is carrying his gun, please read Alice and Bob's story in [the first
chapter in this book](http://www.amazon.com/Introduction-Bioinformatics-
Algorithms-Computational-
Molecular/dp/0262101068/ref=sr_1_1?s=books&ie=UTF8&qid=1376973522&sr=1-1). You
do not need to buy the book. Dr. Pevzner's thoughts are available on free
trial.

