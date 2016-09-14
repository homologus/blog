---
title: Using Bloom Filter - A Simple Introduction for Bioinformaticians
tags:
- Bloom
categories:
- blog
---
For new readers, easiest way to follow us is through our [twitter
feed](https://twitter.com/#!/homolog_us/). The feed is updated, whenever we
post a commentary here.
<!--more-->

Among various techniques for computing k-mer distribution, bloom filter method
is the most memory efficient. We set to write an article about bloom filter,
but found several excellent sources online. Please follow the links at the
bottom of the page to find them. Instead in this space, we shall give you a
very simple analogy to explain the positives and negatives of bloom filter.

Suppose you are writing a paper and want to include references about other
papers in your article. There is no point in including title, authors, year,
journal and every other detail about every reference. You like your reference
to be short, yet informative. One common method is to choose the last name of
the first author and year of publication. This what 'hashing' approach does.

At times, you encounter two papers by two authors with last name Smith
published in the same year 2002. Hashing method will try to break the tie by
including the first name, such as Smith, John 2002 and Smith, Adams 2002.
Instead bloom filter method will not break the tie and refer to both of them
as Smith, 2002.

Bloom filter allows for some false positives. That means if someone wants to
check whether the 2002 paper by a different author, Christopher Smith, has
been cited in your manuscript, he will get 'YES'. On the other hand, **bloom
filter method does not allow for false negatives**. If your paper does not
cite Donaldson 2007, then checking for Donaldson 2007 will give 'NO' and the
answer is definitive.

Bloom filter is helpful in applications, where your RAM or storage is very
expensive and you want to cut down its usage at the cost of some false
positives. Let us present an example. Suppose you are building a website for a
journal, where readers can access and read all bioinformatics-related papers
published the journal. Every time someone accesses information about a paper,
you also show information on other papers in your journal related to the
requested paper such as 'people who read this paper also read those papers'.
The above calculation is done in real time and is computationally intensive.
So, you want to run it, only if you know that the original paper indeed exists
in your database.

If you have limited storage in your web server, you can only store the last
name of authors and years for all papers in your journal and compare those
with new requests. If a new request matches the stored information, you
initiate the resource-intensive calculation. From time to time, false
positives will make you initiate the resource-intensive calculation even
though the requested paper does not exist in your journal. However, you
correct for that error in reporting time. That is a small cost for savings in
storage for your web-server.

Overall, bloom filter offers a trade-off in the above example. That trade-off
is not beneficial to you in the above example, if the cost of performing
resource-intensive calculation is more than additional storage in your web
server. Given that RAM has become the most expensive overhead for NGS
bioinformatics programs, bloom filter seems to offer substantial benefit.

\------------------------------------------------------

You will also find the following pages helpful -

1\. [Using Bloom Filters at
Perl.com](http://www.perl.com/pub/2004/04/08/bloom_filters.html)

2\. [All you ever wanted to know about writing bloom filters - Spyced
Blog](http://spyced.blogspot.com/2009/01/all-you-ever-wanted-to-know-
about.html)

3\. [The Bloom Filter - Mike
James](http://www.i-programmer.info/programming/theory/2404-the-bloom-
filter.html)

