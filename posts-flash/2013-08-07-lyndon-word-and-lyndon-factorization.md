---
title: Lyndon Word and Lyndon Factorization
tags: []
categories:
- blog
---
We came across a very interesting paper, but before we get to it, let us
define few terms with help from wikipedia.
<!--more-->

**Lyndon Word**

> In mathematics, in the areas of combinatorics and computer science, a Lyndon
word is a string that is strictly smaller in lexicographic order than all of
its rotations.

...

****Connection to de Bruijn sequences****

If one concatenates together, in lexicographic order, all the Lyndon words
that have length dividing a given number n, the result is a de Bruijn
sequence, a circular sequence of symbols such that each possible length-n
sequence appears exactly once as one of its contiguous subsequences. For
example, the concatenation of the binary Lyndon words whose length divides
four is

0 0001 0011 01 0111 1

This construction, together with the efficient generation of Lyndon words,
provides an efficient method for constructing a particular de Bruijn sequence
in linear time and logarithmic space.

**[Monoid factorisation and ChenFoxLyndon theorem**](https://en.wikipedia.org/wiki/Chen%E2%80%93Fox%E2%80%93Lyndon_theorem#Chen.E2.80.93Fox.E2.80.93Lyndon_theorem)

> A Lyndon word over a totally ordered alphabet A is a word which is
lexicographically less than all its rotations.[1] The ChenFoxLyndon theorem
states that every string may be formed in a unique way by concatenating a non-
increasing sequence of Lyndon words. Hence taking Xl to be the singleton set
{l} for each Lyndon word l, with the index set L of Lyndon words ordered
lexicographically, we obtain a factorisation of A*.[2] Such a factorisation
can be found in linear time.

Now, we can discuss the paper. Giovanna Rosone, one of the authors, is a
contributor to BCR algorithm that we covered earlier, when Heng Li brought
them to our attention in a comment. Please enjoy the beautiful math of the new
paper.

[Sorting su?xes of a text via its Lyndon
Factorization](http://arxiv.org/pdf/1306.1366.pdf)

> The process of sorting the su?xes of a text plays a fundamental role in Text
Algorithms. They are used for instance in the constructions of the Burrows
Wheeler transform and the su?x array, widely used in several ?elds of Computer
Science. For this reason, several recent researches have been devoted to
?nding new strategies to obtain e?ective methods for such a sorting. In this
paper we introduce a new methodology in which an important role is played by
the Lyndon factorization, so that the local su?xes inside factors detected by
this factorization keep their mutual order when extended to the su?xes of the
whole word. This property suggests a versatile technique that easily can be
adapted to di?erent implementative scenarios.

**"The goal of this paper is to introduce a new strategy for the sorting of the su?xes of a word that opens new scenarios of the computation of the SA and the bwt."**

Do not forget to sit with the following relevant papers (and we presume you
have all relevant BCR papers already):

> This factorization was introduced in [7] and a linear time algorithm is due
to Duval [11]. The intuition that the knowledge of Lyndon factorization of a
text can be used for the computation of the su?x array of the text itself has
been introduced in [5]. Conversely, a way to ?nd the Lyndon factorization from
the su?x array can be found in [17].

[5] S. Bonomo, S. Mantaci, A. Restivo, G. Rosone, and M. Sciortino: Su?xes,
Conjugates and Lyndon words, in DLT, vol. 7907 of LNCS, Springer, 2013, pp.
131142.

[7] K. T. Chen, R. H. Fox, and R. C. Lyndon: Free di?erential calculus. IV.
The quotient groups of the lower central series. Ann. of Math. (2), 68 1958,
pp. 8195.

[11] J.-P. Duval: Factorizing words over an ordered alphabet. Journal of
Algorithms, 4(4) 1983, pp. 363 381.

[17] . C. Hohlweg and C. Reutenauer: Lyndon words, permutations and trees.
Theoretical Computer Science, 307(1) 2003, pp. 173 178.

Tomorrow, we will start again with more interesting math and 10002nd
commandment from NIH !

