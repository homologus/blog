---
title: Linear Probing and Power of Two Choices
tags: []
categories:
- blog
---
The topics covered today are not directly related to any specific
bioinformatics algorithm, but given their widespread use in non-bioinformatics
applications, it is only a matter of time before someone finds a use in
bioinformatics world. Together with [Bloom
filter](http://www.homolog.us/blogs/2012/03/29/using-bloom-filter-a-simple-
introduction-for-bioinformaticians/) and [Cuckoo
hashing](http://www.homolog.us/blogs/2012/10/19/cuckoo-hashing-vs-bloom-
filter/), they form a complete toolbox for uses of hashing.
<!--more-->

**Linear Probing**

[Linear probing](http://en.wikipedia.org/wiki/Linear_probing) is an old
concept for filling up buckets, when collision occurs in a hash table. The
idea behind it is very simple. It says that when collision occurs, check the
next spot in the hash table, next to next one and so on. One can also
generalize the concept of 'next' by using a stepsize.

> Linear probing is a scheme in computer programming for resolving hash
collisions of values of hash functions by sequentially searching the hash
table for a free location.[1] This is accomplished using two values - one as a
starting value and one as an interval between successive values in modular
arithmetic. The second value, which is the same for all keys and known as the
stepsize, is repeatedly added to the starting value until a free space is
found, or the entire table is traversed. (In order to traverse the entire
table the stepsize should be relatively prime to the arraysize, which is why
the array size is often chosen to be a prime number.)

newLocation = (startingValue + stepSize) % arraySize

**Power of Two Choices**

'Power of two choices' came from [PhD thesis (1996) of Michael David
Mitzenmacher](http://www.eecs.harvard.edu/~michaelm/postscripts/mythesis.pdf),
and is applicable to load balancing.

> Suppose that n balls are placed into n bins, each ball being placed into a
bin chosen independently and uniformly at random. Then, with high probability,
the maximum load in any bin is approximately log n/(log log n). Suppose
instead that each ball is placed sequentially into the least full of d bins
chosen independently and uniformly at random. It has recently been shown that
the maximum load is then only (log logn)/(log d +O(1)) with high probability.
Thus giving each ball two choices instead of just one leads to an exponential
improvement in the maximum load. This result demonstrates the power of two
choices, and it has several applications to load balancing in distributed
systems.

Here are two useful links, if you want to learn more -

[The Power of Two Choices - Benny van
Houdt](http://win.ua.ac.be/system/files/vanhoudt_pdf_88534.pdf)

[The Power of Two Random Choices: A Survey of Techniques and Results - Michael
Mitzenmacher  Andrea W.
Richa](http://www.eecs.harvard.edu/~michaelm/postscripts/handbook2001.pdf)

