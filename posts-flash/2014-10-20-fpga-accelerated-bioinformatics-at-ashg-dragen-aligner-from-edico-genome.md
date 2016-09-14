---
title: 'FPGA-accelerated Bioinformatics at #ASHG - Dragen Aligner from Edico Genome'
tags: []
categories:
- blog
---
**We thank Max Shen for his generous contribution to support our blog.**
<!--more-->

\-----------------------------------------------------------

We covered several CPU and GPU-based algorithms in ["ASHG/GA4GH Special - A
Recap of Interesting NGS Algorithms of the
Year"](http://www.homolog.us/blogs/blog/2014/10/18/ashg-special-a-recap-of-
interesting-ngs-algorithms-of-the-year/), but no FPGA-accelerated one. Readers
interested in FPGAs will find the following ASHG abstract interesting. At the
bottom, we discuss the pros and cons of using these three hardware
alternatives in bioinformatics.

[Enhanced fetal aneuploidy detection using hardware accelerated
alignment](http://abstracts.ashg.org/cgi-bin/2014/ashg14s.pl?title=Enhanced%20
fetal%20aneuploidy%20detection%20using%20hardware%20accelerated%20alignment&so
rt=ptimes&sbutton=Detail&absno=140121232&sid=474571)

>

Session Title: Bioinformatics and Genomic Technology Session Type: Poster

Session Location: Exhibit Hall, Ground Level, Convention Center Session Time:
Mon 10:00AM-4:30PM

Program Number: 1675M Presentation Time: Mon, Oct 20, 2014, 2:00PM-3:00PM

Keywords: Bioinformatics and Genomic Technology, KW008 - bioinformatics, KW146
- prenatal diagnosis, KW031 - computational tools, KW103 - massively parallel
sequencing, KW023 - chromosomal abnormalities

M. Sykes1, C. Roddey2, M. Ruehle2, R. McMillen2, P. Whitley1

1) Sequenom Inc., San Diego, CA; 2) Edico Genome Inc., La Jolla, CA.

Noninvasive prenatal testing can be performed by massively parallel sequencing
of DNA from maternal plasma. This method has been shown effective in the
detection of fetal aneuploidies of chromosomes 13, 18, 21 and the sex
chromosomes. Accurate classification of these aneuploidies requires, in part,
alignment of sequencing reads to the human genome, calculation of chromosome
fractions based on these alignments and calculation of z-scores for each
chromosome based on these fractions. The success of these steps relies upon
the choice of aligner and algorithm used to determine the chromosome
fractions.

Here we present reclassification of a dataset of 1269 samples previously
analyzed using bowtie 2 as the aligner. In this study alignments are generated
by the DRAGEN processor, a hardware-accelerated sequencing analysis system
developed by Edico Genome. We report systematic differences between the two
aligners but equivalent performance in terms of chromosome fraction
variability and thus chromosome quantification.

Both the bowtie 2 and DRAGEN based analyses successfully identified all known
T13, T18 and T21 cases in the dataset. The sensitivity and specificity were
both > 99.9% in each classification. At the same time the DRAGEN system
provides speed increases of greater than thirty-fold relative to bowtie 2
running with 6 threads on a 3.5 GHz Xeon CPU, allowing a single computer to
replace the efforts of a small cluster.

These results demonstrate that the classification algorithm for fetal
aneuploidy is robust and resistant to localized changes in the alignment
profile. Furthermore the DRAGEN system provides equivalent performance to
bowtie 2 with a significant increase in speed.

**A Comparison of CPU, GPU and FPGA**

**CPUs**

CPUs are generic processors coming with a small set of hardware-accelerated
commands (e.g. 'add two numbers', 'multiply two numbers', 'compare two
numbers', 'jump to a different statement', etc.). The programmers write code
in a high-level language such as C/C++, and then a compiler translated the
code into the language that the CPU understands. For example, if someone wants
to add five numbers, the compiler will instruct the processor to use 'add two
numbers' command multiple times.

**Advantage** \- Flexibility in coding. If the biological problem changes from the original one, the software code can be tweaked slightly to solve an entirely new problem. The compiler takes care of making sure the tweaked software code is understood by the hardware. 

**Disadvantage** \- Scalability related to memory bandwidth. 

[The Future of Computers Multicore and the Memory
Wall](http://www.homolog.us/blogs/blog/2013/05/05/the-future-of-computers-
multicore-and-the-memory-wall/)

The scalability is not always inherent in the architecture, but comes at times
from programmers lack of knowledge about the hardware architecture. After all,
the promise of software programming is to make the programmers remain
oblivious to what is going inside the chip. However, some programmers do know
quite a bit about the chip, and use their knowledge to get around the memory
bandwidth issue. Here is a beautiful example from Gene Myers -

[In DALIGN Paper, Gene Myers Delivers a Major Blow to His Biggest
Competitor](http://www.homolog.us/blogs/blog/2014/07/28/in-dalign-paper-gene-
myers-delivers-a-major-blow-to-his-biggest-competitor/)

**GPUs**

The computer display is one specific component, where the issue of processing
speed had been most critical. Users were very sensitive to slow displays and
were always ready to pay top dollars for a screen that showed the images
quickly. GPUs were born from that demand. They are highly parallelized
processing chips, except that during most of their early history, GPUs were
only used for processing graphics-related instructions.

**Advantage** Better scalability with large number of parallel executions than CPUs. 

**Disadvantage**

(i) All instructions executing at a time have to be of the same type.

(ii) It is important to have some knowledge of the hardware. The companies are
trying to remove this restriction by coming up with open-CL and other GPU-
specific 'compilers', but it is not possible to take full advantage of the
hardware without knowing how it works.

**FPGA**

FPGAs are hardware chips, which can be reprogrammed to solve any specific
problem.

**Advantage** Speed. 

**Disadvantage** Lack of flexibility and the cost associated with this lack of flexibility. 

Historically, the bioinformatics land had been the graveyard of dead FPGA
companies.

There are two problems -

(i) The algorithmic landscape change too fast,

(ii) The users want to see output from specific programs ('give me results
matching BLAST or HMMER') rather than correct results following the same
algorithm.

Getting back to the current abstract, more details about the technology can be
found [here](http://www.edicogenome.com/dragen/). Based on their numbers, cost
for each accelerated server and associated expenses is around $3M for over 4
years. Are we doing the calculation right? The extra computing cost of each
genome is $1130-$1000=$130 (see below). For 72,000 genomes, the total
computing cost is $9.36M using CPU-based technology (i.e. 50 Dell servers).
With Dragen, they claim the cost savings to be $6M, or the total cost of their
server = $3.36M.

> Earlier this year Illumina announced their HiSeq X Ten, which is a cluster
of 10 HiSeq X instruments capable of sequencing up to 18,000 whole human
genomes each year with continuous operation.

The HiSeq X Ten has a run cycle of ~3 days and produces ~150 genomes each run
cycle. This means that the data generated must be analyzed within 3 days or a
backlog will occur. Simple math thus provides a target of ~28 minutes for the
completion of the mapping, aligning, sorting, deduplication and variant
calling of each genome.

Running the industry standard BWA+GATK analysis pipeline to perform this
analysis on a reasonably high-end (Dual Intel Xeon E5-2697v2 CPU 12 core, 2.7
GHz with 96 GB DRAM) compute server takes ~24 hours per genome. To achieve the
required throughput of 150 genomes every three days, at least 50 of these
servers are required.

With DRAGENs run time for the full pipeline being well under 28 minutes, only
a single card is required to handle the data produced by a full HiSeq X Ten
system running at maximum capacity!

When calculating the costs associated with the legacy compute server
infrastructure required to analyze and store the data produced by the HiSeq X
Ten, we use the same method that Illumina themselves use to calculate their
$1,000 Genome. Equipment costs are amortized over 4 years and staff and
overheads are included.

By taking into account standard pricing from Dell for the 50 compute servers,
industry standard costs for associated IT professionals, rack space and power,
as well as AWS pricing for upload and storage of the genomic data over a 4
year period, the $1,000 Genome becomes a $1,130 Genome.

By comparison, DRAGEN significantly reduces the compute cost over the same
period while also removing the need for IT professionals and lowering power
and rack space requirements. In addition, since DRAGEN implements CRAM-based
compression within its pipeline to transparently compress the large amounts of
data to be uploaded and stored for later re-analysis, these costs are also
significantly lower. When combining all of these savings over the 72,000
genomes sequenced during the 4 year period, DRAGEN provides cost savings of
~$6 million!

