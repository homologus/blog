---
title: Burrows Wheeler transform, Suffix Arrays and FM Index
tags:
- compression
- bowtie
- BWT
- BWA
categories:
- blog
---
Our dear reader [Nils
Homer](http://www.nilshomer.com/index.php?title=Research) suggested FM-index
as a follow-up topic in our discussions on Burrows Wheeler transform. [FM-
index](http://en.wikipedia.org/wiki/FM-index) is an important component of
Bowtie algorithm allowing it to obtain small memory footprint for the indices.
In this commentary, we shall give you a list of important developments in
computer science related to pattern searching so that you know the historical
context of those discoveries. The presentation here will consist of a set of
links and brief explanation of why the algorithm was a major improvement over
the existing landscape. In the subsequent posts, we shall go into details of
some of those algorithms related to NGS search.
<!--more-->

Before I start, here are few things to keep in mind about computer algorithms.
You may wonder about what factors lead to selection of one algorithm over
other competing ones. Speed of the algorithm is one obvious factor. The
algorithm must do its task much faster than other alternatives, and computer
scientists have a mathematical way to define what is 'much faster'. It is
called [order of the algorithm](http://en.wikipedia.org/wiki/Big_O_notation),
and is measured by the increase in time to operate on bigger and bigger sets.
If an algorithm takes 10 hours to process 1 million reads, 40 hours to process
2 million reads and 90 hours to process 3 million reads, the order of the
algorithm is O(N^2). The amount of time grows quadratically with the number of
reads. That is less preferable than an O(N) algorithm, where the amount of
time is proportional to the number of reads.

The second factor in deciding about an algorithm is the amount of RAM it
takes. We talked about this extensively in our discussions on de Bruijn
assemblers. Here also you can define order of the algorithm in terms of growth
of RAM usage with bigger and bigger input sets.

The third factor that is never mentioned in computer science textbooks is
whether the algorithm is patented. This was a key factor in widespread
adoption of Burrows Wheeler transform in data compression. BWT algorithm was
not patented, and Mr. Burrows and Mr. Wheeler never intended ('threatened') to
do so, whereas arithmetic compression algorithms were patented by IBM and
other parties.

Next, we shall discuss various important discoveries related to string search
algorithms. Let me define the problem at the outset. We want to find out,
whether a string such as 'ATGGTGTGGAT' is present within a very large string
'TTATAGGT...............GTGGA' - likely a genome. At this point, we only care
about exact matches. Insertions, deletions and modifications will be handled
later.

**Dumbest algorithm**

The dumbest algorithm that you can think of will start from one end of the
genome and look for pattern matches, until it finds one or reaches the other
end of the genome. For a large genome and large number of reads, this process
takes for ever and you realize that a smart solution is needed. Computer
scientists reached that point in 1970s and came up with the solution called
'suffix tree'.

**Suffix tree - 1976**

If you are unfamiliar with the term computer science term 'suffix', if means
all subwords of a word that go from anywhere in the middle of the word to its
end. For 'homolog.us', the suffixes are 'homolog.us', 'omolog.us', 'molog.us',
'olog.us', 'log.us', 'og.us', 'g.us', '.us', 'us' and 's'.

Before covering suffix tree, let me give you the general idea behind speeding
up the search process. As we explained before, you need to construct an index
of the genome and utilize the index to guide your search. For example, you can
store the locations of all 11-mers in the genome in an 'index array'. For
searching, you first compare the read with the 'index array', and then conduct
full pattern matching sin genomic regions referenced by the index array. This
method definitely speeds up the search process, but it adds two additional
complexities - (i) the **time** taken to build up the index and (ii) **space**
needed for the index.

Suffix trees were the most elegant approach for building and storing the
index. A greatly simplified version of constructing suffix trees was presented
in a paper by Edward McCreight in 1976. I found [this
link](http://marknelson.us/1996/08/01/suffix-trees/) most helpful on suffix
trees.

**Suffix array- 1989**

As you remember, space and time were two important factors for constructing
suffix trees or any other indices of large strings. The space issue was
greatly improved by discovery of [suffix
arrays](http://en.wikipedia.org/wiki/Suffix_array) by Gene Myers and Udi
Manber in 1989. Does the name Gene Myers seem familiar? He was one of the
authors of the seminal BLAST paper by Altschul.

**Ukkonen's algorithm - 1995**

Ukkonen developed a [linear time
algorithm](http://en.wikipedia.org/wiki/Ukkonen's_algorithm) for generating
suffix trees and dramatically improved the time needed to construct the trees.

**Burrows Wheeler transform - 1994**

We already covered Burrows Wheeler transform in our previous commentaries.
This transform takes an input string and turns it into something else. Why is
that great? (i) because the procedure is reversible, (ii) the transformed
string can be compressed more easily than the original one.

Burrows Wheeler transform may appear unrelated to the previous discoveries
that we listed until you realize that the procedure for generating Burrows
Wheeler transform is very similar to the method for generating suffix array.

**FM index - 2000**

'FM' in the name stands for the names of the authors. In 2000, Ferragina and
Manzini published a paper titled 'Opportunistic Data Structures with
Applications', where they proposed a data structure to combine the best of
Burrows Wheeler transformation-based data compression and suffix arrays. In
their method, the reference sequence can be kept compressed, and there is no
need to decompress the whole sequence for pattern searching. One can search
for pattern in a large reference by only decompressing a small part of it and
comparing for matches. This resulted in significant reduction in storing the
index without any cost to time needed for pattern searching.

Few other algorithms appear promising and we may update the above list by
adding them, but for the time being, we shall leave you with the above set of
historical developments.

