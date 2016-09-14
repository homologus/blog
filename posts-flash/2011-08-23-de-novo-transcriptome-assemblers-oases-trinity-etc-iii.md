---
title: De Novo Transcriptome Assemblers &ndash; Oases, Trinity, etc. &ndash; III
tags:
- de-bruijn
- transcriptome assembly
- oases
- velvet
- Trinity
categories:
- rnaseq
---
**Oases and Trinity Quick Start Guide**
<!--more-->

This guide is for those, who like to get started quickly with available
transcriptome assemblers. So far, our experiences had been with Oases and
Trinity only. If we become familiar with other transcriptome assemblers, this
guide will be expanded.

**Oases**

Oases is the transcriptome arm of Velvet, a popular de Bruijn graph-based
genome assembler.

Where do we download it from?

Please use following links - [Velvet](http://www.ebi.ac.uk/~zerbino/velvet/),
[Oases](http://www.ebi.ac.uk/~zerbino/oases/)

How do we run it?

First compile and install Velvet and Oases. Then, run Velvet assembler on your
reads just like you would do for genome assembly, but **remember to add
-read_trkg option**. After Velvet completes, run oases.

Is there a guide with step-by-step instructions?

The instruction manuals at [Velvet](http://www.ebi.ac.uk/~zerbino/velvet/) and
[Oases](http://www.ebi.ac.uk/~zerbino/oases/) website are very helpful. Also,
[here](http://ged.msu.edu/angus/tutorials-2011/mrnaseq-assembly.html) is a
nice guide with step-by-step instruction on how to run the programs. Advanced
users are recommended to join Velvet and Oases mailing lists at
[this](http://www.ebi.ac.uk/~zerbino/velvet/) and [this
link](http://www.ebi.ac.uk/~zerbino/oases/) for more complex questions.

Memory requirement

Oases is very memory intensive and requires even more RAM than the genome
assembler Velvet. For a paired-end library of ~7M (100ntx2) reads, Oases used
~50-55Gb RAM.

Running Time

Velvet+Oases run much faster than Trinity, the other transcriptome assembler
we cover here. Assembly time for a paired-end library of ~7M (100ntx2) reads
is typically about 5-6 hours.

**Trinity**

Trinity is a stand-alone de Bruijn graph-based de novo transcriptome assembler
from Broad institute. It is combination of three programs Inchworm (C++),
Chrysalis (C++) and Butterfly (Java). You can read the story behind its
development [here](http://www.broadinstitute.org/blog/suite-tools-takes-
flight).

Where do we download it from?

Please use the following link -
[Trinity](http://trinityrnaseq.sourceforge.net/)

How do we run it?

Afterdownload, type make in the trinity base directory to compile Inchworm and
Chrysalis. Butterfly, being written in Java, does not need any compilation.
Then, run ./run_Trinity.sh on your reads with appropriate options. Please **do
not forget to add -run_butterfly option.**

Is there a guide with step-by-step instructions?

Yes, it is right [here](http://trinityrnaseq.sourceforge.net/).

Memory requirement

Trinity needs about 20-24Gb RAM for a library with 7.5M (100nt x2) paired end
reads (please check our [forum](http://homolog.us/smf) for an example).

Running Time

Trinity takes about 24 hours to assemble transcriptome from a sequence library
with 7.5M (100nt x2) paired end reads (please check our
[forum](http://homolog.us/smf) for an example).

We have been writing on various topics for a while, but are not sure whether
you find them useful. If you do not like to use public comment section, please
feel free to email us at samanta at homolog.us.

