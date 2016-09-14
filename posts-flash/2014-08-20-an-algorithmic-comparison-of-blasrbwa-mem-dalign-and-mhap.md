---
title: An Algorithmic Comparison of BLASR&#47;BWA-MEM, DALIGN and MHAP
tags: []
categories:
- blog
---
The problem of assembling a large number of noisy long reads is expected to
show up, no matter whether one uses Pacbio or nanopore long read technology.
The good news is that it is possible to do the assembly and the quality is a
lot better than what can be achieved with short reads or even Sanger reads at
far higher cost. The latest MHAP paper has excellent demonstration of this
point regarding the Drosophila genome.
<!--more-->

With that knowledge, let us look at the biggest informatics challenge at hand
and that is how to align many read pairs against each other. To visualize the
scale of the problem, if one plans to assemble human genome from 5kB reads
with 50x coverage, that means he will have to work with about 30 million
reads. Aligning those 30 million reads all against all is the most time-
consuming step in the assembly. That means 30 million x 30 million = 900
trillion alignments of very noisy reads, where Smith-Waterman is the most
viable approach.

How to do 900 trillion alignments of long read pairs? The answer is simple -
don't do it, and that is where the main innovation of BLASR/BWAMEM, DALIGN and
MHAP come in. All three methods pick only a subset of read pairs to do the
actual alignment, and that subset is selected based on sharing of unusually
large number of k-mers between read pairs. The difference between the
algorithms is in how they find those shared k-mers. To compare the time-
performances of the algorithms, one needs to understand both mathematical
aspects of the respective methods and the hardware-related issues, because a
large amount of data are being swapped between hard-disk, memory and processor
during the course of execution.

**DALIGN**

[Gene Myers' DALIGN](http://www.homolog.us/blogs/blog/2014/07/28/in-dalign-
paper-gene-myers-delivers-a-major-blow-to-his-biggest-competitor/) uses the
most straightforward method. It takes a subset of reads, finds all kmers along
with their locations, sorts them and identifies matching pairs. Sorting is the
most time-consuming step here, and Myers uses the speed difference between L1
cache and RAM to build a clever sorting algorithm that keeps data within the
L1 cache. That can give one 100x boost in access time over RAM, and moreover
the conflict between processors is not an issue, because each processor has
its own L1 cache.

**BLASR/BWA-MEM**

BLASR and BWA-MEM use Burrows Wheeler transform and FM index of the collection
of reads and then finds shared kmers by doing BWT-based perfect match
alignment.

There are three difficulties here compared to DALIGN.

(i) Unlike human genome, where the reference is fixed, the BWT of reads have
to be constructed again and again for every read library and that adds to the
cost of alignment.

(ii) BWT-based FM index is saved in the RAM and it randomizes the locations
compared to the genomic locations. Therefore, the RAM access is effectively
random and slows down the process.

(iii) If one has many processors aligning many reads in parallel, memory
bandwidth becomes the major bottleneck, because each processor wants to align
its own segment with the index in the RAM.

**MHAP**

[MHAP](http://www.homolog.us/blogs/blog/2014/08/15/after-hgap-and-spades-
comes-new-pacbio-assembler-mhap/) creates a hash table of kmers in a read and
attempts to find other matching ones based on the number of hash collisions. I
think that is essentially what their algorithm boils down to after you remove
all bells and whistles about MinHash sketch. If my interpretation is correct,
maybe one can even get rid of the MinHash sketch and simply use a one-
dimensional hash.

Here is the problem. The number of comparisons in their approach will scale as
N^2, whereas the scaling will be closer to N or N.log(N) for other two
approaches (ignoring the insignificant cost of BWT construction for BWAMEM and
BLASR). [Edit. the claim about N^2 is wrong, as Adam points out in the
supplement.]

Am I missing something here?

\-----------------------

Edit.

1\. The author of MHAP responds:

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/08/Capture3-300x201.png)

2\. I asked Gene Myers about this post, and he mentioned that there is a third
component ('verifier') after 'kmer filtering' and 'alignment' that my blog
post did not mention. He also pointed out that verifier takes the most time
among all, and should be subject to algorithm development and optimization.
Here is his full email -

> One thing that isn't correct though it that the majority of the time taken
by DALIGN and all of these tools, is for computing and verifying an alignment
between two reads once a pair of reads has been identified as possibly
matching. That is, the computation is divided into a "filter" that as
efficiently as possible identifies pairs of reads that might have a
local/overlap alignment, followed by a "verifier" that determines if the pair
actually share a local alignment and delivers the alignment.

The verify takes 80%-90% of the time for DALIGN. MHAP and BLASR both spend a
lot of effort focused on making the filter fast, which is not the main issue
because most of the time is in the verifier. You do not describe the verifiers
for the three methods and that is the important part of the problem ! Also the
authors of MHAP and BLASR also don't seem to understand that this is where the
optimization effort should be going.

