---
title: Strategies for Perfect Hash and Minimal Perfect Hash
tags: []
categories:
- blog
---
For an introductory blog post, try Steve Hanov.
<!--more-->

[Throw away the keys: Easy, Minimal Perfect
Hashing](http://stevehanov.ca/blog/index.php?id=119)

If you have more time to explore, Botelho's thesis is possibly the best place
to go to.

[Near-Optimal Space Perfect Hashing
Algorithms](http://cmph.sourceforge.net/papers/thesis.pdf)

> In this thesis we present a simple, highly scalable and near-space optimal
perfect hashing algorithm. Evaluation of a PHF on a given element of S
requires constant time, and the dominating phase in the construction algorithm
consists of sorting n ?ngerprints of O(log n) bits in O(n) time. The space
usage depends on the relation between m and n. For m = n the space usage is in
the range 2.62n to 3.3n bits, depending on the constants involved in the
construction and in the evaluation phases. For m = 1.23n the space usage is in
the range 1.95n to 2.7n bits. In all cases, this is within a small constant
factor from the information theoretical minimum of approximately 1.44n bits
for MPHFs and 0.89n bits for PHFs, something that has not been achieved by
previous algorithms, except asymptotically for very large n. This small space
usage opens up the use of MPHFs to applications for which they were not useful
in the past.

Also some useful papers (from Botelho) -

[An Approach for Minimal Perfect Hash Functions for Very Large
Databases](http://cmph.sourceforge.net/papers/tr06.pdf)

> We propose a novel external memory based algorithm for constructing minimal
perfect hash functions h for huge sets of keys. For a set of n keys, our
algorithm outputs h in time O(n). The algorithm needs a small vector of one
byte entries in main memory to construct h. The evaluation of h(x) requires
three memory accesses for any key x. The description of h takes a constant
number of up to 9 bits for each key, which is optimal and close to the
theoretical lower bound, i.e., around 2 bits per key. In our experiments, we
used a collection of 1 billion URLs collected from the web, each URL 64
characters long on average. For this collection, our algorithm (i) ?nds a
minimal perfect hash function in approximately 3 hours using a commodity PC,
(ii) needs just 5.45 megabytes of internal memory to generate h and (iii)
takes 8.1 bits per key for the description of h.

[Simple and Space-E?cient Minimal Perfect Hash
Functions](http://www.liacs.nl/~graaf/STUDENTENSEMINARIUM/SSEM.pdf)

>

**Abstract.** A perfect hash function (PHF) h : U ? [0, m ? 1] for a key set S is a function that maps the keys of S to unique values. The minimum amount of space to represent a PHF for a given set S is known to be approximately 1.44n2/m bits, where n = |S|. In this paper we present new algorithms for construction and evaluation of PHFs of a given set (for m = n and m = 1.23n), with the following properties: 

1\. Evaluation of a PHF requires constant time.

2\. The algorithms are simple to describe and implement, and run in

linear time.

3\. The amount of space needed to represent the PHFs is around a

factor 2 from the information theoretical minimum.

No previously known algorithm has these properties. To our knowledge, any
algorithm in the literature with the third property either:

Requires exponential time for construction and evaluation, or

Uses near-optimal space only asymptotically, for extremely large n.

Thus, our main contribution is a scheme that gives low space usage for
realistic values of n. The main technical ingredient is a new way of basing
PHFs on random hypergraphs. Previously, this approaach has been used to design
simple PHFs with superlinear space usage.

Finally, a hash-related paper by someone from USA - que sorpresa !!

[GPERF A Perfect Hash Function Generator - Douglas C.
Schmidt](http://www.cse.wustl.edu/~schmidt/PDF/gperf.pdf)

> Perfect hash functions are a time and space ef?cient implementation of
static search sets. A static search set is an abstract data type (ADT) with
operations initialize, insert, and retrieve. Static search sets are common in
system software applications. Typical static search sets include compiler and
interpreter reserved words, assembler instruction mnemonics, shell interpreter
built-in commands, and CORBA IDL compilers. Search set elements are called
keywords. Keywords are inserted into the set once, usually off-line at
compile-time. gperf is a freely available perfect hash function generator
written in C++ that automatically constructs perfect hash functions from a
user-supplied list of keywords. It was designed in the spirit of utilities
like lex [1] and yacc [2] to remove the drudgery associated with constructing
time and space ef?cient keyword recognizers manually.

