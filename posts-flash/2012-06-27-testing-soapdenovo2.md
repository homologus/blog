---
title: Testing SOAPdenovo2 Pre-release Version
tags:
- SOAPdenovo
categories:
- blog
---
Yesterday morning, we received by email a soon-to-be-released copy of
SOAPdenovo2 executable for testing purpose. The email came from a gentleman
named ???.
<!--more-->

What is the first big test we ran after receiving the email? Yes, we used
google and [wiktionary](http://en.wiktionary.org/wiki/Wiktionary:Main_Page) to
translate each character of the name into pinyin.

? - xie

? - yin

? - long

Another google search with words 'xie yin long BGI' told us that the email
came from [Dr. Yin Long Xie, Senior Bioinformatician of
BGI](http://www.eurekalert.org/pub_releases/2011-11/bs-cgg111211.php). Great,
we now have an 'English face' !!

Believe it or not, the above step was the hardest in our entire execution of
SOAPdenovo2. The program ran flawlessly on the Illumina reads with a large and
complex eukaryotic genome (vertebrate, not mammal). Let me detail the steps.

**Opening the zip file:**

The zip file 'SOAPdenovo2.zip' expanded into two programs -

i) pregraph_sparse_63mer.5.1

ii) SOAPdenovo-63mer-v2.04.3

The second program runs in similar manner as the good old
[SOAPdenovo](http://soap.genomics.org.cn/soapdenovo.html), whereas the first
program is an additional module to run SOAPdenovo with less RAM. In the words
of Dr. ???,

>

Anyone who received the SOAPdenovo2 copy (attachment "SOAPdenovo2.zip") please
note that there is another program "pregraph_sparse_63mer.5.1" inside it. The
"pregraph_sparse_63mer.5.1" is a new optional module in SOAPdenovo2 which
would save ~60% memory consumption for the first step (pregraph). Also note
that new algorithm is applied in this module and the contigs and scaffolds may
not exactly the same as the original one. If you want to try it, please
substitute this module for the "SOAPdenovo pregraph". The usage is attached.

You may run it like this:

./pregraph_sparse [parameters]

./SOAPdenovo-63mer contig [parameters]

./SOAPdenovo-63mer map [parameters]

./SOAPdenovo-63mer scaff [parameters]

If you have no idea about how large the genome is, you'd better to have a kmer
analysis(kmer frequency distribution) to estimate the genome size before
assembly.

Or set a relatively large number to have a try first, adjust it if the step
failed. For reference, it's suitable to set -z 5000000000 for human(3Gbp
genome).

**Preparing the config file:**

Our input data consists of two Illumina libraries -

(i) a mate pair library with 300 million x 2 reads (99 nt)

(ii) a paired end library with 450 million x 2 reads

Information on those sequencing libraries need to be given in a config file
for SOAPdenovo2. Format of the config file remains the same as SOAPdenovo. You
can find detailed explanation
[here](http://soap.genomics.org.cn/soapdenovo.html).

Here is our config file:

>

max_rd_len=99

[LIB]

avg_ins=225

reverse_seq=0

asm_flags=3

rank=1

q1=runPE_1.fq

q2=runPE_2.fq

[LIB]

avg_ins=2000

reverse_seq=1

asm_flags=2

rank=2

q1=runMP_1.fq

q2=runMP_2.fq

It is very simple. First line gives the maximum read length. Then information
on two libraries are given. In a previous commentary, we explained [inward and
outward-looking reads](http://www.homolog.us/blogs/2012/02/19/illumina-paired-
end-libraries-inward-and-outward-looking-reads/). The parameter reverse_seq is
0 for inward looking reads (typically for paired end), and 1 for outward-
looking reads (typically for mate pairs).

To explain the remaining parameters, we quote [SOAPdenovo
website](http://soap.genomics.org.cn/soapdenovo.html):

> Libraries with the same "rank" are used at the same time for scaffolding in
the order indicated by "rank".

The flag "asm_flag" has three eligible values: 1 (reads only used for contig
assembly), 2 (only used for scaffold assembly) and 3 (used for both contig and
scaffold assembly).

There are two types of paired-end libraries: a) forward-reverse, generated
from fragmented DNA ends with typical insert size less than 800 bp; b)
reverse-forward, generated from circularizing libraries with typical insert
size greater than 2 Kb. User should set parameter for tag "reverse_seq" to
indicate this: 0, forward-reverse; 1, reverse-forward.

**Running the program:**

SOAPdenovo runs in four steps.

i) preparing the pregraph. This step is similar to velveth for velvet.

ii) Determining contigs. This step is similar to velvetg for velvet.

iii) Mapping back reads on to contigs.

iv) Assembling contigs into scaffolds.

All steps ran smoothly with SOAPdenovo2. Ideally, you can run 'SOAPdenovo2 all
[params]' and let SOAPdenovo2 run four steps one by one. We chose to run them
individually to utilize sparse pregraph module.

Our commands -

./pregraph_sparse_63mer.5.1 -s config_file -K 45 -p 28 -z 1100000000 -o outPG

./SOAPdenovo-63mer-v2.04.3 contig -g outPG

./SOAPdenovo-63mer-v2.04.3 map -s config_file -g outPG -p 28

./SOAPdenovo-63mer-v2.04.3 scaff -g outPG -p 28

The complete run took about 4 or 5 hours, among which mapping back of reads
onto contigs took the longest. We only checked RAM usage from time to time,
and do not believe it exceeded 60-70G any time.

How good is the assembly? The genome size came out to be 560 Mbp. Longest
scaffold is 886,512 nt long. Going back to our old statistics, N50 at contig
stage is 1531 nt and at scaffold stage is 104,253 nt.

We will do further tests on the quality of the assembly, and update you here.
Stay tuned !!

