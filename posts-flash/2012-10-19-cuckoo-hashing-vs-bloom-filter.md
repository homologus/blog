---
title: Cuckoo Hashing vs Bloom Filter
tags: []
categories:
- blog
---
We noticed that the SPAdes code uses Cuckoo hashing in its code. What is
[Cuckoo hashing](http://en.wikipedia.org/wiki/Cuckoo_hashing)?
<!--more-->

> The basic idea is to use two hash functions instead of only one. This
provides two possible locations in the hash table for each key. In one of the
commonly used variants of the algorithm, the hash table is split into two
smaller tables of equal size, and each hash function provides an index into
one of these two tables.

When a new key is inserted, a greedy algorithm is used: The new key is
inserted in one of its two possible locations, "kicking out", that is,
displacing, any key that might already reside in this location. This displaced
key is then inserted in its alternative location, again kicking out any key
that might reside there, until a vacant position is found, or the procedure
enters an infinite loop. In the latter case, the hash table is rebuilt in-
place using new hash functions:

There is no need to allocate new tables for the rehashing: We may simply run
through the tables to delete and perform the usual insertion procedure on all
keys found not to be at their intended position in the table.

Pagh & Rodler, "Cuckoo Hashing"[1]

Lookup requires inspection of just two locations in the hash table, which
takes constant time in the worst case (see Big O notation). This is in
contrast to many other hash table algorithms, which may not have a constant
worst-case bound on the time to do a lookup.

Bloom filters (discussed [here](http://www.homolog.us/blogs/2012/03/29/using-
bloom-filter-a-simple-introduction-for-bioinformaticians/) and
[here](http://www.homolog.us/blogs/2012/03/28/efficient-methods-for-
counting-k-mers/)) also use multiple hashes, but that is the only similarity
between two methods. Here is a [good discussion on their
differences](http://stackoverflow.com/questions/867099/bloom-filter-or-cuckoo-
hashing) \-

> Which do you prefer, wine or cheese? A Bloom filter is for when you have
limited space, high query cost, and mostly negative queries. In that case, a
BF with 8 bits per key and 4 hash functions gives you 2.5% false positive
rate; you process queries nearly 40 times faster than before, at the cost of 1
byte per key. On the other hand, if any of the previous conditions do not
hold, a hash table acting as a cache makes sense, though it obviously will
take a lot more than one byte per entry :-) You can even skip over the hard
edge cases of cuckoo hashing if it's a cache. That also makes the size-
increase problems of cuckoo hash tables (or anything other than linear hash)
moot. my2c

Our knowledgeable readers can provide further insight on which one is better.

