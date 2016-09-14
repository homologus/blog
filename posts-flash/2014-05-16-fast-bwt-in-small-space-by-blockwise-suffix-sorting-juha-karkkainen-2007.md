---
title: Fast BWT in Small Space by Blockwise Suffix Sorting (Juha K&auml;rkk&auml;inen
  - 2007)
tags: []
categories:
- blog
---
This is an old but very useful paper by Juha Krkkinen that we are looking into
to understand the BGI paper ["GPU-Accelerated BWT Construction for Large
Collection of Short Reads"](http://www.homolog.us/blogs/blog/2014/01/29/gpu-
accelerated-bwt-construction-large-collection-short-reads/) posted a few
months back.
<!--more-->

[Fast BWT in small space by blockwise suffix
sorting](http://www.sciencedirect.com/science/article/pii/S0304397507005245)

> We present a new space- and time-efficient algorithm for computing the
BurrowWheeler transform (BWT). For any choice of a parameter v?[3,n2/3], the
computation of BWT for a text of length n takes O(nlogn+vn) worst-case time
and View the MathML source average-case time using View the MathML source bits
of space in addition to the text and the BWT. For example, if v=log2n, the
time is O(nlog2n) in the worst case and O(nlogn) on an average with the
additional space requirement of O(n) bits. The algorithm is alphabet-
independent: it uses only character comparisons, and the complexities do not
depend on the alphabet size unless v does. A practical implementation is 23
times slower than one of the fastest and most space-efficient previous
algorithms while needing only one-third of the main memory. The algorithm is
based on suffix arrays, but unlike any other algorithm, it can construct the
suffix array a small block at a time without storing the rest of the suffix
array anywhere.

If you are more interested, the following code may come handy.

[bwt-blockwise](https://code.google.com/p/bwt-blockwise/)

> This project is an implementation of the blockwise Burrows-Wheeler transform
algorithm described in "Fast BWT in small space by blockwise suffix sorting,"
Karkkainen, (2007). This implementation is specialized for DNA sequences,
meaning an alphabet consisting only of {A, C, G, T}. The advantage of the
blockwise BWT over other algorithms is the space efficiency of the procedure,
which is controlled by a user-specified parameter v. The complexity is O(nlogn
+ vn) time and O(nlogn/sqrt(v)) space in addition to storing the original
string and the resulting BWT. Space efficiency is important in the analysis of
DNA sequences, which can be long enough such that storing all of the sequences
in memory is infeasible.

Also, Ben Langmead's website has a set of slides [with simple introduction](ht
tps://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&cad=rja&uact=8&v
ed=0CCcQFjAA&url=http%3A%2F%2Fwww.cbcb.umd.edu%2Fconfcour%2FSpring2008
%2FCMSC858P-materials%2Fben-presentation.ppt&ei=sHd2U_SXJpHYoATo84CoCQ&usg=AFQ
jCNGQa9TxUTU6JT7R4t2RGAJh4xi8gQ&sig2=E6GivGzww6WhWuDKMZ08ug&bvm=bv.66917471,d.
cGU).

