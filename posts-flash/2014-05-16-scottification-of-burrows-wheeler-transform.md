---
title: Scottification of Burrows Wheeler Transform
tags: []
categories:
- blog
---
The story of David Scott's discovery of bijective improvement to Burrows
Wheeler transform is quite fascinating. His name will probably not ring a bell
in the vaunted world of academia, ([where 'big talkers' like Ewan Birney get
to become Fellow of Royal Society](http://sandwalk.blogspot.com/2014/05/what-
did-encode-consortium-say-in-2012.html)), he is nobody. His own website [gives
the following bio](http://bijective.dogma.net/index.htm)\-
<!--more-->

> David A. Scott is not a writter and this is his first attempt at writting an
article of this type. I graduated from Arizona State University with a BSEE in
Electrical Engineering with a major in Fields and Waves. This was the closest
thing to a Math Degree without all the English requirements. My main carreer
was writting and debugging algorithms for the NAVY at CHINA LAKE CA. form 1970
to 1996. While at CHINA LAKE I was sent to The University of Southern
California in 1972 to recieve my MSEE in Electrical Engineering the major
field of study was control theroy. I am currently retired living in El Paso,
Texas; in the near future I may pursue more education in Jaurez to become a
medical doctor.

Yet, in the real world of intellectual contributions, his discovery will last
a lot longer that ENCODE. Naturally, his discovery was not announced through a
paper, but a comment in a discussion forum. As the story goes, around 2006 or
2007, he posted a message in the encryption-related mailing lists [describing
his improvement to BWT](http://bijective.dogma.net/compresa.htm).

> This page looks at a modified BWT compression package and suggests that the
mods make for a better transform than the standard BWT. I called this
bijective version a BWT that has been Scottified. It is what the BWT should
have been. If one looks at only the transformed data without the index the old
original BWT most likely leads to a better compression. But when you consider
the need for an index to be passed along the BWTS transform will lead on the
average to better compression.

Soon some mathematicians started to poke around and found that he indeed had a
new way of computing BWT-like transform with two useful features -

(i) It is bijective without the added $ sign at the end.

(ii) Through Lyndon factorization, his method can be parallelized easily. We
discussed about Lyndon word and Lyndon factorization [here](Lyndon Word and
Lyndon Factorization).

A Google engineer joined him to put together a formal paper, which can be
found at the following link.

[A Bijective String Sorting Transform](http://arxiv.org/abs/1201.3077)

> Given a string of characters, the Burrows-Wheeler Transform rearranges the
characters in it so as to produce another string of the same length which is
more amenable to compression techniques such as move to front, run-length
encoding, and entropy encoders. We present a variant of the transform which
gives rise to similar or better compression value, but, unlike the original,
the transform we present is bijective, in that the inverse transformation
exists for all strings. Our experiments indicate that using our variant of the
transform gives rise to better compression ratio than the original Burrows-
Wheeler transform. We also show that both the transform and its inverse can be
computed in linear time and consuming linear storage.

Apparently, the above proof has several errors, whereas the following paper is
mathematically correct.

[On Bijective Variants of the Burrows-Wheeler Transform - Manfred
Kufleitner](http://arxiv.org/abs/0908.0239)

> The sort transform (ST) is a modification of the Burrows-Wheeler transform
(BWT). Both transformations map an arbitrary word of length n to a pair
consisting of a word of length n and an index between 1 and n. The BWT sorts
all rotation conjugates of the input word, whereas the ST of order k only uses
the first k letters for sorting all such conjugates. If two conjugates start
with the same prefix of length k, then the indices of the rotations are used
for tie-breaking. Both transforms output the sequence of the last letters of
the sorted list and the index of the input within the sorted list. In this
paper, we discuss a bijective variant of the BWT (due to Scott), proving its
correctness and relations to other results due to Gessel and Reutenauer (1993)
and Crochemore, Desarmenien, and Perrin (2005). Further, we present a novel
bijective variant of the ST.

Those, who do not like formal mathematics may enjoy the really simple
introduction in [zephyrtronium's github
page](https://github.com/zephyrtronium/bwst). It comes with the added benefit
of code that you can download.

> The Burrows-Wheeler-Scott transform (called the Burrows-Wheeler transform
"Scottified" in existing literature, but that sounds silly) sorts together all
infinitely repeated cycles of each Lyndon word of the input, then takes the
last character of each rotation of each Lyndon word in the overall sorted
order. Of course, this description is about as intelligible as any of the
existing literature on it for someone not intimately familiar with the
concepts involved, and incomplete for someone who is.

Lyndon words are sequences which are less than any of the rotations of that
sequence. "Less than", that is, the order, is defined in "the usual
lexicographical way": 'a' < 'b' by definition; 'aa' < 'ab' because the first
positions are the same and the second position is lesser in 'aa'; 'ab' < 'ba'
because 'ab' is lesser in the first position. For now, the order of sequences
whose lengths are not equal is left undefined.

A Lyndon word is a sequence such that no matter how many times you take the
rightmost (or leftmost) element and attach it to the left (or right,
respectively), the result is never less than the word. By the Chen-Fox-Lyndon
theorem, every ordered sequence has a unique "Lyndon factorization" of Lyndon
words, such that each word in the factorization is never greater than its
predecessor, where order is here (not for the BWST algorithm) defined for
words of unequal length such that if a is a prefix of b, then a < b.

