---
title: Perfect Hash Algorithm of Meraculous Assembler
tags: []
categories:
- blog
---
Today we are going through the codes of [Meraculous assembler from
JGI](http://www.homolog.us/blogs/2012/08/16/genome-assembly-mermaid-and-
meraculous/), which has many similarities with [Minia
algorithm](http://www.homolog.us/blogs/2012/10/01/minia-assembly-algorithm-
and-french-revolution/) described in earlier commentary. The biggest
difference is that, instead of Bloom filter, they use a perfect hash as
explained in the following text and figure [taken from their paper](http://www
.plosone.org/article/info:doi%2F10.1371%2Fjournal.pone.0023501#pone.0023501.s0
02):
<!--more-->

![](http://www.plosone.org/article/fetchObject.action?uri=info:doi/10.1371/jou
rnal.pone.0023501.g002&representation=PNG_M)

> To dramatically reduce the memory requirement for meraculous, we developed a
novel perfect static hashing scheme that can be applied whenever the complete
set of keys is known initially and does not change during the use of the hash,
as is the case with the U-U deBruijn graph for a given shotgun dataset. In
contrast, general dynamic hashing schemes typically retain the flexibility to
add new (key, value) combinations at any time. Our hashing scheme is perfect
in the sense that the average lookup time does not depend on the genome size.
For a genome of size G, our hash requires only ~e*G bytes of memory,
independent of the choice of k, where e = 2.71828 is base of natural
logarithms. The U-U hash for a human genome then requires only ~8 Gb, a
~60-fold memory savings relative to a standard hash and well within the range
of many desktop systems.

Our perfect hash h(u) is constructed using a preprocessing step that
iteratively identifies and progressively eliminates collisions for all U-U
k-mers (Methods). Let hi(u) be a series of independent hash functions defined
on k-mers. Each hash function hi(u) returns an integer between 1 and Hi that
is assumed to be uniformly distributed over that range. Then a perfect hash
h(u) can be defined iteratively as follows. First, compute h1(u) for all U-U
k-mers, and record all collisions. Applying the Poisson distribution,
H1*exp(?G1/H1) k-mers do not collide. For such k-mers, we assign a hash level
of 1, and define the perfect hash by h(u) = h1(u). The G2 = G1?H_1*exp(?G1/H1)
k-mers that collide at level 1 are then hashed at the second level using an
independent hash function h2(u) with a reduced range H2. Those that do not
collide are assigned h(u) = H1+h2(u); those that do collide are passed to the
third level. This process is iterated until there are no more collisions.

The result is a perfect hash h(u) that, by construction, has no collisions.
Since each of the input U-U k-mers is uniquely mapped by this function, we do
not need to store the key k-mer with each entry, and need only store the
value, which is just a single nucleotide. This results in a memory savings of
order 1/k.

Seems too complicated? We will expand on this commentary as we work through
their code.

**Perfect hash**

In a regular hashing scheme, the **hash functions are fixed** and **data is
dynamically allocated**. For a NGS library, we know beforehand, which k-mers
will go into the hash, because we can run a k-mer counting step before
assembly. So, the set of k-mers going into the hash table is fixed. Can we
choose the hash functions dynamically to avoid all collisions?

The scheme works in the following manner.

First, a hash function is chosen, all k-mers are run through it, and those
k-mers not hitting collision are used up (allocated).

Then, a second hash function is chosen, all remaining k-mers are run through
it, and those k-mers not hitting collision are used up (allocated).

The above steps continue with third, fourth, fifth...hash functions, until all
k-mers are allocated. If we have 10 hash functions at that point, a 'perfect'
hash designed with those 10 hash functions will avoid all collisions for the
fixed set of k-mers being allocated.

Real simple, huh?

[To be continued]

