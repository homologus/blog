---
title: '"Why We Didn''t Use a Bloom Filter"'
tags: []
categories:
- blog
---
Bloom-filter bashing day? :)
<!--more-->

[Why We Didn't Use a Bloom Filter](http://www.dr-josiah.com/2012/03/why-we-
didnt-use-bloom-filter.html)

> DRAM is actually really slow. When you make a request to read DRAM, it
returns a 64 byte cache line from that region in about 15 nanoseconds (in the
best case). That's around 4.3 gigs/second random access. If you are accessing
memory in a predictable pattern, the second block you request is returned in
about 10 nanoseconds, and subsequent blocks can be returned in as fast as 3-4
nanoseconds. So, after the first few "slow" requests, you can read at a peak
rate of roughly 21.3 gigs/second for predictable access patterns on high end
machines.

Back to our case. We intersected a set of 5 million items against a set of 7.5
million items in 6 milliseconds. Doing the math... 4 bytes * (5m + 7.5m) / 6ms
-> 8.3 gigs/second. So, we were within a factor of ~2-2.5x of maxing out the
memory bandwidth available to the entire system with our 6ms intersection.

Let's pretend that we had already built a bloom filter, and let's even say
that the math said that we only need 7 probes (the reality would probably be
closer to 16 or so). At 15ns per probe, because bloom filters have
unpredictably random access patterns, 7 probes per 5 million users in our
input set, my math says that the intersection would take 525 milliseconds,
which is 87 times slower than our intersection method.

But here's the other nasty bit of reality; constructing the bloom filter for
that 5 million entry set (because we need to have bloom filter for all sets)
takes at least twice as long as querying it. Why? Because to update 1 bit in
the filter, you first need to read the cache line, then you need to update the
bit in the register, then you need to write the data back. I know what you are
thinking, you are thinking that your write-through cache will help you. But
you are wrong. Because you are writing randomly to your bloom filter, you run
out of cache very quickly, and the caching layers within your processor will
quickly start blocking the processor from reading or writing to memory,
because it's got a backlog of data to flush to memory that is limited to 15ns
per random write. So with a (lower-bounded) 525ms to intersect, that's roughly
1.05 seconds to construct the bloom filter in the best case.

Meanwhile, the slow O(nlogn) standard C sort() finishes in 1.2 seconds, which
is within spitting distance of the theoretically optimal bloom filter we just
described. We also only sort once, but intersect thousands of times, so even
if it did offer a modest performance advantage, it wouldn't be worth the
performance penalty during intersection.

Another drawback with the bloom filter is memory. I know what you are
thinking, you are thinking "well, with a 7 probe bloom filter, maybe you only
need 2-3 bytes per user, instead of the 4 bytes per user". But in order to
perform the intersection, you still need your list of users (sorted or not) in
addition to the bloom filter, leaving you with 6-7 bytes per user.

Conclusion: bloom filters would be (80-160 times) slower to intersect, would
use more memory, don't offer a significant construction time performance
advantage (probably closer to 2x slower for a 16 probe bloom filter), and are
only approximately correct.

\-------------------

Not really.

2006:

[Less Hashing, Same Performance: Building a Better Bloom Filter - Adam Kirsch
and Michael
Mitzenmacher](http://www.eecs.harvard.edu/~kirsch/pubs/bbbf/esa06.pdf)

> A standard technique from the hashing literature is to use two hash
functions h1(x) and h2(x) to simulate additional hash functions of the form
gi(x) = h1(x) +ih2(x). We demonstrate that this technique can be usefully
applied to Bloom ?lters and related data structures. Speci?cally, only two
hash functions are necessary to e?ectively implement a Bloom ?lter without any
loss in the asymptotic false positive probability. This leads to less
computation and potentially less need for randomness in practice.

2007:

[Cache-, Hash- and Space-E?cient Bloom Filters - Felix Putze, Peter Sanders,
Johannes Singler](http://algo2.iti.kit.edu/singler/publications
/cacheefficientbloomfilters-wea2007.pdf)

> A Bloom ?lter is a very compact data structure that supports approximate
membership queries on a set, allowing false positives. We propose several new
variants of Bloom ?lters and replacements with similar functionality. All of
them have a better cache-e?ciency and need less hash bits than regular Bloom
?lters. Some use SIMD functionality, while the others provide an even better
space e?ciency. As a consequence, we get a more ?exible trade-o? between false
positive rate, spacee?ciency, cache-e?ciency, hash-e?ciency, and computational
e?ort. We analyze the e?ciency of Bloom ?lters and the proposed replacements
in detail, in terms of the false positive rate, the number of expected
cachemisses, and the number of required hash bits. We also describe and
experimentally evaluate the performance of highly-tuned implementations. For
many settings, our alternatives perform better than the methods proposed so
far.

2008:

[Why Simple Hash Functions Work: Exploiting the Entropy in a Data Stream -
Michael Mitzenmachery Salil
Vadhanz](http://www.eecs.harvard.edu/~michaelm/postscripts/soda2008b.pdf)

> Hashing is fundamental to many algorithms and data structures widely used in
practice. For theoretical analysis of hashing, there have been two main
approaches. First, one can assume that the hash function is truly random,
mapping each data item independently and uniformly to the range. This
idealized model is unrealistic because a truly random hash function requires
an exponential number of bits to describe. Alternatively, one can provide
rigorous bounds on performance when explicit families of hash functions are
used, such as 2-universal or O(1)-wise independent families. For such
families, performance guarantees are often noticeably weaker than for ideal
hashing.

In practice, however, it is commonly observed that simple hash functions,
including 2-universal hash functions, perform as predicted by the idealized
analysis for truly random hash functions. In this paper, we try to explain
this phenomenon. We demonstrate that the strong performance of universal hash
functions in practice can arise naturally from a combination of the randomness
of the hash function and the data. Specically, following the large body of
literature on random sources and randomness extraction, we model the data as
coming from a \block source," whereby each new data item has some \entropy"
given the previous ones. As long as the (Renyi) entropy per data item is
suciently large, it turns out that the performance when choosing a hash
function from a 2-universal family is essentially the same as for a truly
random hash function. We describe results for several sample applications,
including linear probing, balanced allocations, and Bloom filters.

\----------------------------------------

Also check -

[Generalized Bloom Filters - Rafael P. Laufer, Pedro B. Velloso, and Otto
Carlos M. B. Duarte](https://www.gta.ufrj.br/ftp/gta/TechReports/LVD05d.pdf)

Please note the first link at the top of the page has a point. When you
implement a program with many memory accesses, memory bandwidth and latency
start to dominate the performance. Given that a Bloom filter accesses memory d
times for each k-mer and given that those d accesses are random in memory
space, Bloom filter can reduce the memory performance significantly. Then
again, if memory is your limiting factor, you need to have a solution, and
memory performance becomes secondary.

