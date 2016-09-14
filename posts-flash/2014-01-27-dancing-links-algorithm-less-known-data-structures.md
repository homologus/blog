---
title: Dancing Links Algorithm and Less Known Data Structures
tags: []
categories:
- blog
---
Thanks to Stephen Turner, we came across a [very informative question-answer
set from stackoverflow](http://stackoverflow.com/questions/500607/what-are-
the-lesser-known-but-useful-data-structures?rq=1).
<!--more-->

Question:

> Everybody knows about linked lists, binary trees, and hashes, but what about
Skip lists and Bloom filters for example. I would like to know more data
structures that are not so common, but are worth knowing because they rely on
great ideas and enrich a programmer's tool box.

PS: I am also interested in techniques like Dancing links which make clever
use of properties of a common data structure.

Few highlighted examples -

1\. [Dancing Links](http://en.wikipedia.org/wiki/Dancing_Links)

> In computer science, Dancing Links, also known as DLX, is the technique
suggested by Donald Knuth to efficiently implement his Algorithm X.[1]
Algorithm X is a recursive, nondeterministic, depth-first, backtracking
algorithm that finds all solutions to the exact cover problem. Some of the
better-known exact cover problems include tiling, the n queens problem, and
Sudoku.

The name Dancing Links comes from the way the algorithm works, as iterations
of the algorithm cause the links to "dance" with partner links so as to
resemble an "exquisitely choreographed dance." Knuth credits Hiroshi
Hitotsumatsu and K?hei Noshita with having invented the idea in 1979,[2] but
it is his paper which has popularized it.

2\. [Tries](http://en.wikipedia.org/wiki/Trie)

> In computer science, a trie, also called digital tree and sometimes radix
tree or prefix tree (as they can be searched by prefixes), is an ordered tree
data structure that is used to store a dynamic set or associative array where
the keys are usually strings. Unlike a binary search tree, no node in the tree
stores the key associated with that node; instead, its position in the tree
defines the key with which it is associated. All the descendants of a node
have a common prefix of the string associated with that node, and the root is
associated with the empty string. Values are normally not associated with
every node, only with leaves and some inner nodes that correspond to keys of
interest. For the space-optimized presentation of prefix tree, see compact
prefix tree.

3\. [Rope](http://en.wikipedia.org/wiki/Rope_%28data_structure%29)

> In computer programming a rope, or cord, is a data structure for efficiently
storing and manipulating a very long string. For example, a text editing
program may use a rope to represent the text being edited, so that operations
such as insertion, deletion, and random access can be done efficiently.[1]

Check Heng Li's ropebwt for an example.

There is [plenty more in the page](http://stackoverflow.com/questions/500607
/what-are-the-lesser-known-but-useful-data-structures?rq=1) including skip
lists, spatial indices, zippers, lock-free queues and other possibilities.

