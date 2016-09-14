---
title: Good C++ Development Practices in Sailfish Code
tags: []
categories:
- blog
---
Contributed by our judge, [who voted for Sailfish in Best of
2013](http://www.homolog.us/blogs/blog/2014/01/20/announcing-results-
best-2013/).
<!--more-->

\----------------------------------------------

[Sailfish](http://www.cs.cmu.edu/~ckingsf/software/sailfish/index.html) is a
good example of neat, modern NGS software development. I looked at the code
and found some gems.

1\. The Makefile (Cmake) is excellent:

\- [It automatically downloads and installs dependencies, i.e.

CMPH (for perfect hashing) and Jellyfish.

\- It can even [automatically download and install boost](https://github.com/k
ingsfordgroup/sailfish/blob/master/CMakeLists.txt#L100) without root.

This, I think, removes the only obstacle that generally prevent us from using
boost in our softs.

2\. The ingredient that seems to make Sailfish fast is minimal perfect
hashing, instead of classical hash table lookups. This works for static hash
tables only. They use the existing CMPH library for perfect hashing, [so the
code in Sailfish is just a

wrapper.

3\. [They use
TBB](https://github.com/kingsfordgroup/sailfish/search?q=tbb&ref=cmdform) for
various multi-core operations and data structures.

E.g. parallel-for, thread-safe hash table, set, queue. For instance parallel-
for has the [potential to be
faster](http://stackoverflow.com/questions/7130020/intel-tbb-vs-boost) than
naively parallelizing using threads with e.g. Boost.

4\. They use Boost, but not so much. The replaced the lock-free queue of Boost
with the one from TBB. The only Boost functions widely used are filesystems
operations and range operations. Just in [this file ](https://github.com/kings
fordgroup/sailfish/blob/faa252a0ab2cfe29b89693a96ab8007b0face894/include/Colla
psedIterativeOptimizer.hpp) they use some boost data structures:
dynamic_bitset and accumulators (for stats).

Smaller details:

1\. [The default Fasta file reader](https://github.com/kingsfordgroup/sailfish
/blob/faa252a0ab2cfe29b89693a96ab8007b0face894/src/IndexedCounter.cpp#L475) is
Jellyfish's, and it falls back to kseq whenever the input is exotic (named
pipe). So perhaps Jellyfish's fasta parser is even faster than kseq? Reading
fasta files quickly is quite important for performance.

2\. [The software tells the user](https://github.com/kingsfordgroup/sailfish/b
lob/605498ab6dcc66d908db0f51f1d39a1104a72dbc/src/VersionChecker.cpp) whenever
a new version

is available (but doesn't auto-update itself).

3\. [The command line handling](https://github.com/kingsfordgroup/sailfish/blo
b/faa252a0ab2cfe29b89693a96ab8007b0face894/src/Sailfish.cpp#L89) is clean.

4\. It uses C++11 so gcc-4.7 is required. It's probably OK to use C++11 in
today's software development. The main developer of Sailfish has a good
understanding of c++11, he made a small tutorial of its new features on its
github: [https://github.com/rob-p/cpp11fun/tree/master/src](http://www.cs.cmu.
edu/~ckingsf/software/sailfish/index.html).

