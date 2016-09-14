---
title: In DALIGN Paper, Gene Myers Delivers a Major Blow to His Biggest Competitor
tags: []
categories:
- blog
---
![polls_Boxers_2_5840_794020_answer_1_xlarge](http://www.homolog.us/blogs/wp-
content/uploads/2014/07/polls_Boxers_2_5840_794020_answer_1_xlarge-
300x270.gif)
<!--more-->

While Gene Myers was busy working on neural images of fruitflies, he noticed
the bioinformatics land being taken over by search algorithm originating from
a 'competitor'. Now he comes back with an outstanding paper (DALIGN) to show
why he is still the master.

That competitor of Gene Myers is none other than Gene Myers, 20 years younger.
In early 90s, he and [Udi Manber](https://en.wikipedia.org/wiki/Udi_Manber)
(currently leading the search group at Google) introduced the concept of
suffix arrays. Fast forward by two decades, every nucleotide search program
for new sequencing technologies uses suffix arrays, combined with BWT
transform and FM indices. We covered that history in an earlier commentary
(check [this blog post from 2011](http://www.homolog.us/blogs/blog/2011/10/20
/burrow-wheeler-transform-suffix-arrays-and-fm-index/)).

Myers tried to use BLASR, which incorporated suffix arrays, for aligning
PacBio reads and found it to be too slow. The troubles come from memory
bandwidth and cache incoherence. Modern processors have three levels of cache
(L1, L2, L3) and the speed difference between having all data in L1 cache vs
DRAM can be 100x. BWT-based FM index algorithm makes effectively random
accesses to memory locations and therefore the search process gets highly
dependent on DRAM access. Especially when one tries to scale BWT-based
alignment programs with multiple cores, memory bandwidth becomes the major
bottleneck. Our readers are well familiar with that drawback (Check ["The
Future of Computers Multicore and the Memory
Wall"](http://www.homolog.us/blogs/blog/2013/05/05/the-future-of-computers-
multicore-and-the-memory-wall/)).

The algorithm proposed by Myers overcomes that bottleneck in two steps. They
are so elegant that even the memory-heavy part of his algorithm sees 3.6x
scaleup in a 4-core machine, whereas the less memory-intensive part sees 3.88x
scaleup. The steps are - (i) finding read pairs highly likely to align based
on matching seeds and (ii) alignment. Even though they sound innocuous, the
beauty is in the details. The memory-intensive rapid seed detection part
introduces a highly cache-coherent radix sort algorithm that attempts to keep
relevant bits in L1 cache. The rapid local alignment part uses Myers' own
O(nd) algorithm from mid-80s (see ["How Does the Unix Diff Algorithm
Work?"](http://www.homolog.us/blogs/blog/2014/07/25/how-does-the-unix-diff-
algorithm-work/)) , but with several optimization steps to limit the rapidly
expanding parallel waves at every step of search. Especially it makes use of
random distribution of errors in PacBio reads.

What next after this formidable accomplishment of speeding up PacBio alignment
25X over BLASR and thus making large assemblies possible? There are rumors
that Gene Myers plans to demonstrate one or more of the following three - (i)
walk over water on river Elbe, (ii) design a perfect assembler, (iii) finish
the zebrafish genome. Given how difficult (ii) and (iii) turned out to be so
far, we believe he will go for (i).

If, instead, Myers plans to finish Danio and thousands of other recently
published incomplete genomes, he needs to hurry up. We heard that Udi Manber,
who is currently at Google, is working on a different solution for those bad
genomes. Google plans to replace all NNNNNN regions with targeted ads, and
there is a possibility that Google will buy a short-read company, because more
gaps, the better.

`

>chr1

atgtcgcggcgcaatgggaggagatttaaaNNNNNNN.....Get..2%interest...rate...for..your..
.mortgage.........NNNNNNNttccttctttaaattattaggtgcgcgctagcgatcgcggtattatataNNNN
NNNNNNNNN.....Domino's....Free...Pizza....Delivery.........NNNNNNNccattgccaggt
ccggcgctaggcgctagcgcgctaggcgcgcgcccctatgagga`

The full article by Myers will appear in [WABI 2014 (Workshop on Algorithms in
Bioinformatics), Sept 8-10, Wroclaw,
Poland](http://algo2014.ii.uni.wroc.pl/wabi/). In the meanwhile, readers
interested to know more about his developments can check [his
blog](http://dazzlerblog.wordpress.com/2014/07/10/dalign-fast-and-sensitive-
detection-of-all-pairwise-local-alignments/). The code of DALIGNER is
available [from github](https://github.com/thegenemyers/DALIGNER).

