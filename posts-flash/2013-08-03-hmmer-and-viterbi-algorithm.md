---
title: HMMER and Viterbi Algorithm
tags: []
categories:
- blog
---
We have been going through the code of HMMER. It is an alignment algorithm
that makes use of Hidden Markov Models to search for homolog.us proteins and
nucleotides. If you are not aware, HMMER3.0 is completely rewritten from its
slower version HMMER2.0 and supposedly runs as fast as BLAST. For details,
please take a look at Sean Eddy's 2011 PLOS 2011 paper.
<!--more-->

[Accelerated Profile HMM Searches](http://www.ploscompbiol.org/article/info%3A
doi%2F10.1371%2Fjournal.pcbi.1002195)

Today's commentary is not about HMMER, but about Andrew Viterbi, whose
algorithm is the core part of HMMER. Andrew Viterbi was a very smart professor
of Electrical Engineering at UCLA, who came up with the algorithm in 1967.
Viterbi never patented the algorithm.

[Error bounds for convolutional codes and an asymptotically optimum decoding a
lgorithm](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=1054010&url=ht
tp%3A%2F%2Fieeexplore.ieee.org%2Fxpls%2Fabs_all.jsp%3Farnumber%3D1054010)

> The probability of error in decoding an optimal convolutional code
transmitted over a memoryless channel is bounded from above and below as a
function of the constraint length of the code. For all but pathological
channels the bounds are asymptotically (exponentially) tight for rates
aboveR_{0}, the computational cutoff rate of sequential decoding. As a
function of constraint length the performance of optimal convolutional codes
is shown to be superior to that of block codes of the same length, the
relative improvement increasing with rate. The upper bound is obtained for a
specific probabilistic nonsequential decoding algorithm which is shown to be
asymptotically optimum for rates aboveR_{0}and whose performance bears certain
similarities to that of sequential decoding algorithms.

A little bit on Viterbi's life:

<iframe width="560" height="315" src="http://www.youtube.com/embed/3hkT0Xtqlc8" frameborder="0"> </iframe>

If he was so smart, why did he not write something similar to HMMER? Well, as
it turns out, he wrote NIH grant to apply his algorithm for bioinformatics,
but it did not get funded.

Haha...did you fall for it? Here is the real story. Andrew Viterbi and his
friend Irwin Jacobs (another electrical engineer) left teaching to start a
semiconductor company named [Qualcomm](http://en.wikipedia.org/wiki/Qualcomm).

> Qualcomm was founded in 1985 by MIT alumnus and UC San Diego professor Irwin
M. Jacobs, USC and MIT alumnus Andrew Viterbi, Harvey White, Adelia Coffman,
Andrew Cohen, Klein Gilhousen, and Franklin Antonio. Jacobs and Viterbi had
previously founded Linkabit. Qualcomm's first products and services included
the OmniTRACS satellite locating and messaging service, used by long-haul
trucking companies, developed from a product called Omninet owned by Parviz
Nazarian and Neil Kadisha, and specialized integrated circuits for digital
radio communications such as a Viterbi decoder.

Qualcomm is undoubtedly one of the best semiconductor companies. It makes very
critical chips to reduce noise in mobile phones.

HMMER took a different turn:

![](http://hmmer.janelia.org/static/images/hmmer_titlebar_small.gif)

