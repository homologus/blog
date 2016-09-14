---
title: Generalizing the Burrows-Wheeler Transform
tags: []
categories:
- blog
---
We recovered [this
paper](ftp://ftp.math.hkbu.edu.hk/pub/techreport/math427.pdf) from a ftp site
and do not know whether it is published in any journal. Ge Nong , who did very
good work on Burrows Wheeler transform, is an author. The text in bold
(emphasis ours) caught our attention. Did anyone take a look at Schindler
Transform?
<!--more-->

> The Burrows-Wheeler Transform (BWT) has been long known as a superior
reversible text transform method based on block sorting strategy. **Among all,
the Schindler Transform (ST) is the most remarkable variant of BWT for it
dramatically boosts the transform speed using a partial context sorting
scheme.** The inverse ST currently requires the use of a hash table, which is
not indispensable for the inverse BWT. In this paper, we show that both the
BWT and the ST can actually be ?t into a uni?ed algorithm framework in the
sense that not only can the BWT and the ST be performed using a same
algorithm, but also can the inverse BWT and the inverse ST be performed
similarly without any hash table. Speci?cally, we prove several theorems and
derive from them two ef?cient algorithms for inverting the ST. The proposed
algorithms solve the inverse ST with a time complexity of O(kN) and a space
complexity of O(N), where N is the texts length, k 2 [1; N] is the context
order of the transform and is typically very small compared to N in practice.
As a result, the algorithms used for the inverse BWT has been successfully
generalized to solve the inverse ST.

The relevant paragraph on Schindler Transform is included below.

> **The Schindler Transform**

Obviously, the need of sorting all the contexts up to their full lengths of N
is the main cause for the super-linear time complexity of BWT. Inspired by
this observation, Schindler proposed11 in [10], [20] a slightly different
transform which can sort the texts by using only their ?rst k characters
(where k can be a value far less than N), but still render itself reversible.
The key idea of ST is a two-hierarchy priority sorting scheme, i.e. the
lexicographical sorting criterion in tandem with the positional sorting
criterion. To be more speci?c, let OM be the same matrix as de?ned for the
BWT, using the k-order ST, OM is transformed to Mk by sorting all its rows
according to their ?rst k left characters only, i.e. the k-order contexts. In
case that any two k-order contexts are equal, the tie is resolved by their
positions in the original OM. This two-level sorting scheme can be done using
radix sort as follows.

Edit.

We found the reference of original paper.

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture24-300x63.png)

and [some more info on Dr. Chan's
research](http://uic.edu.hk/isci/news/chair/070.html?height=300&width=500) \-

> From Burrows-Wheeler Transform to Suffix Array Construction

Speaker: Dr. Daricks W.H. Chan

Time: 2:00pm-3:00pm, May 8th, 2013

Venue: E202

Abstract:

In 1994, Burrows and Wheeler presented a block-sorting based transform in
their technical report [Burrows and Wheeler 1994], known as the BWT, which
permutes a text into a new sequence that usually is more compressible.
Briefly, given a text S of N characters, the BWT can be performed in three
steps: (1) to derive a matrix consisting of N rotations (cyclic shifts) of S;
(2) to sort the rows of the matrix lexicographically; and (3) to extract the
last column of the sorted matrix to produce the transformed text. The BWT is
lossless and reversible. There exists an efficient algorithm which can
correctly restore the original text S from the transformed text with a
time/space complexity of O(N). Therefore, when N is large, any naive sorting
scheme will still impose an evident bottleneck on the BWT.

One drawback of the BWT in its original form is its time and space
complexities. Any naive implementation of the second step that utilizes
general purpose comparison-based sorting algorithms could result in a O(N^2
log N) worst case running time complexity. If a traditional radix sort
algorithm is used, it requires O(N^2). One solution proposed by Schindler in
[Schindler 1997; 2001], known as ST, to speed up the block sorting is to sort
only the first k columns of the matrix in order to reduce the complexity to
O(kN). A major tradeoff for the ST to achieve the speedup gain over the BWT is
that the inverse ST is far more complicated than the inverse BWT. In
Schindler's patent disclosure [Schindler 2001], the hash table based inverse
ST algorithms were given only for the orders of 1 and 2. In [Chan and Nong
2006] and [Nong, Zhang and Chan 2011], we show that the time complexity of the
inverse ST is independent of k and gave a linear time algorithm to the inverse
ST.

Our study was then extended to the construction of suffix array SA(S) of the
text S. SA(S) is an array of pointers for all the suffixes in the S sorted in
the lexicographically ascending order. It is clear that BWT and the suffix
array construction on S is equivalent. In the talk, I will also introduce the
development of linear suffix array construction algorithms in the last decade.

CV of Dr. Chan

Dr. Daricks W.H. Chan is now serving the Department of Mathematics and
Information Technology of the Hong Kong Institute of Education as an assistant
professor. Before joining HKIEd, Dr. Chan taught in the Department of
Mathematics of Hong Kong Baptist University, and he had been teaching
mathematics subjects in various levels for over ten years. He obtained his
doctorate from the HKBU in 2003, and the postgraduate diploma in education
from the CUHK in 1999. His areas of expertise are algorithm design, quantum
information, graph theory and combinatorics. Dr. Chan has published over
fourty papers in international journals including SIAM, IEEE, Physical Review
and Discrete Applied Mathematics. He was awarded research and teaching grants
of total amount over two million Hong Kong dollars.

