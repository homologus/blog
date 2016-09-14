---
title: Using Mathematical Induction to Design Algorithms
tags: []
categories:
- blog
---
We are revisiting the 1980s, thanks to Gene Myers, and came across [this
elegant 1988 paper by Udi Manber](http://dl.acm.org/citation.cfm?id=50091)
that our readers may find helpful. Manber later wrote a book "Introduction to
Algorithms - A Creative Approach", where he expanded on the same ideas (more
on that later).
<!--more-->

>

This article presents a methodology, based on mathematical induction, for
approaching the design and the teaching of combinatorial algorithms. While
this methodology does not cover all possible ways of designing algorithms it
does cover many known techniques. It also provides an elegant intuitive
framework for explaining the design of algorithms in more depth. The heart of
the methodology lies in an analogy between the intellectual process of proving
mathematical theorems and that of designing combinatorial algorithms. We claim
that although these two processes serve different purposes and achieve
different types of results, they are more similar than it seems. This claim is
established here by a series of examples of algorithms, each developed and
explained by the use of the methodology. We believe that students can get more
motivation, greater depth, and better understanding of algorithms by this
methodology.

Mathematical induction is a very powerful proof technique. It usually works as
follows. Let T be a theorem that we want to prove. Suppose that 7 includes a
parameter n whose value can be any natural number. Instead of proving directly
that T holds for all values of n we prove that (1) T holds for n = 1, and (2)
T holds for any n > 1 provided that T holds for n - 1. The first part is
usually very simple to prove. Proving the second part is easier in many cases
than proving the theorem directly since we can use the assumption that T holds
for n - 1. (In some sense we get this assumption for free.) In other words, it
is enough to reduce the theorem to one with a smaller value of n, rather than
proving it from scratch. We concentrate on this reduction. The same principle
holds for algorithms. Induction allows one to concentrate on extending
solutions of smaller subproblems to those of larger problems. One starts with
an arbitrary instance of the problem at hand, and tries to solve it by using
the assumption that the same problem but with smaller size has already been
solved. For example, given a sequence of n > 1 numbers to sort (it is trivial
to sort one number), we can assume that we already know how to sort n - 1
numbers. Then we can either sort the first n - 1 numbers and insert the nth
number in its correct position (which leads to an algorithm called insertion
sort), or start by putting the nth number in its final position and then sort
the rest (which is called selection sort). We need only to address the
operation on the nth number. (Of course, this is not the only way to sort, nor
is it the only way to use induction for sorting.)

Speaking of Manber's book, [here](http://www.amazon.com/review/R1BG5NGZFNFXIE/
ref=cm_cr_pr_viewpnt#R1BG5NGZFNFXIE) is an useful review by a reader at
Amazon. We emphasized the most important part.

> This book is much more than a catalog of algorithms (e.g., CLR): its purpose
is to train your intuition to recognize mathematical structure in abstract
problems. What does it matter if you know Dijkstra's algorithm? It's much more
valuable to have good intuitions and a inductive reasoning tool chest with
which to smash apart all of the variations of the shortest path problem (for
example.)

The reviewers who wrote that the book "assumes you are a math wiz" and that it
provides "little or no guidance for solving an arbitrary problem of the same
type" didn't get it. This book is trying very hard to make you into a wiz by
forcing you to really interact with mathematics, rather than working through a
set of nearly identical problems (--what passes for "education" in North
America.)

I was just going to leave my review at that, but since the reviews that people
find "helpful" are so way off base, I think I should throw in a relevant
story.

**When my friend was in grade 11, he showed up to the Canadian Computing Competition finals, placing 14th. The guy who won told him, "if you want to win, read this book." Two years later, he won the CCC against 2000 other students. This book is the best introduction you can give a budding mathematician.**

Sure, you can cough up what you've memorized from CLR during your university
algorithms course. But, do you want to learn to invent algorithms yourself?

Math is not something handed down generations in big, dry textbooks. Like all
knowledge, math is organically discovered Truth, and you have learn to
discover it for yourself.

