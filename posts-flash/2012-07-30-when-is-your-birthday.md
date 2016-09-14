---
title: When is your birthday?   (on hashing, sparsehash and murmurhash)
tags: []
categories:
- blog
---
Imagine you are giving a talk to a small group of 40 persons, and start with
asking everyone his/her birthday. What are the chances that two members in the
audience will have the same birthday? The answer is ~90% !! Yes, in 9 out of
10 cases, a small group of 40 people will have at least one pair with common
birthday. The answer defies common intuition, but [can be proven
mathematically](http://en.wikipedia.org/wiki/Birthday_problem).
<!--more-->

How is asking everyone's birthday related to NGS bioinformatics? The same kind
of question is asked, when we try to design optimal hashing strategy to store
data. Suppose you like to save all 21-mers from a small set of reads. You have
estimated by some other means that the total number of 21-mers is around
50,000. If you allocate a large array to store all possible 21-mers, that
array takes 4^21= 4.4 trillion memory spaces to save only 50,000 entities. The
method is inefficient, because a large amount of memory will be wasted. Using
hash data structure is a good solution in the above scenario.

How does a hash work? It runs a function ('hash function') on each k-mer and
converts it into an integer pointing to a location in a table. The size of the
table is comparable to the expected number of entities (50,000 in above
example), and very little space is wasted.

The birthday example can demonstrate well, how hashing works. Let us say you
like to store information on all people attending your talk, and want to
access it by using the names of people. A data structure with every possible
name in the world is wastage of space. So, one possibility is to have a data
structure with 366 spots, each representing a day of the year. The data for
each person will be stored in the space allocated at his birthday. Asking for
each person's birthday works as the hash function.

Real life data like nucleotide sequences do not have birthdays, and need some
other kind of hash functions. [Designing a good hash
function](http://code.google.com/p/smhasher/wiki/SMHasher) is more art than
science. It has to run fast and it has to randomize all input strings within
the allocated space. [Murmurhash](https://sites.google.com/site/murmurhash/)
is one of the most efficient hash function at present, and you can check its
code at the google link or get some hint
[here](http://stackoverflow.com/questions/1057036/please-explain-murmur-hash).

Based on the birthday example, you can see that collision is the biggest
potential problem with hashing. When two persons have the same birthday, they
try to reference the same spot in the table and that is a problem. You either
need to increase the size of the table, or add extra code to resolve
collision. The surprising part is how little the table is filled (only 40
persons out of 366 potential birthdays) before you have substantial chance
(~90%) of collision.

[Google sparsehash](http://code.google.com/p/sparsehash/) is a very efficient
open source library that you can use to solve your hashing problems. It is
used by NGS assembler ABySS.

