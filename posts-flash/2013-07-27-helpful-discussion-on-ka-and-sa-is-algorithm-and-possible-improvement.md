---
title: Helpful Discussion on KA and SA-IS Algorithm and Possible Improvement
tags: []
categories:
- blog
---
'[Yangzhe1990's Blog'](http://yangzhe1990.wordpress.com/2012/11/04/ka-and-
induced-sorting-which-is-faster/) has nice discussion on KA and SA-IS
algorithms and Yuta Mori's implementation.
<!--more-->

>

In mid September, I started writing a internal tool for my employer, which
requires suffix tree. So I went to check if there are any new faster
algorithms after the O(n) skew algorithm for building suffix array and O(n)
Ukkonens algorithm for building suffix tree online.

I only found a little publications of suffix array during the 9 years between
2003 and 2012, which seems to indicate that this field is inactive. And its
also funny that the skew algorithm has a new name DC-3?. The publications we
are talking about in this article are:

Pang Ko and Srinivas Aluru, Space Efficient Linear Time Construction of Suffix
Arrays, 2003;

Ge Nong, Sen Zhang and Wai Hong Chan, Two Efficient Algorithms for Linear
Suffix Array Construction, 2008.

What got us interested was this claim -

> Even yuta256 has compared the KAs algorithm, he didnt notice that the
potential power behind the KAs algorithm which will beat his sais-lite in
future.

We are still trying to understand his argument. If you have any insight,
please let us know. IT he refers to is the [Itoh-Tanaka paper found here](http
://web.iiit.ac.in/~abhishek_shukla/suffix/In%20Memory%20Suffix%20Array%20Const
ruction.pdf).

SA-IS and KA algorithms are for O(n) construction of suffix arrays, and thus
BWT. They are [not patented unlike Illumina's BCR
algorithm](http://www.homolog.us/blogs/blog/2013/07/20/bioinformatics-patents-
on-burrows-wheeler-transform/), although admittedly they deal with two
different kinds of sequences. Speaking of BWT patents, we contacted Dr.
Anthony Cox asking what other bioinformaticians should do to use his approach,
but have not heard back from him yet.

\----------------------------

Useful slides from Manzini (click on image to view pdf file) -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/07/Capture27-300x169.png)

\----------------------------

Nong Ge is an author of the SA-IS algorithm.

![Nong](http://seq.cbrc.jp/ISCB-Asia2012/schedule/PCinvitePages/GeNong.jpg)

[Here](http://www.cs.sysu.edu.cn/nong/old_index.htm) is his webpage at the Sun
Yat-sen university.

\------------------------------

Who is the current winner? [Stackexchange
says](http://stackoverflow.com/questions/7857674/whats-the-current-state-of-
the-art-suffix-array-construction-algorithm) livdivsort by Yuta Mori or
[archon40 by kvark](http://www.kvatom.com/archon). [Here](https://code.google.
com/p/libdivsufsort/source/browse/trunk/README?r=15) are the benchmarks. Also,
[this page](http://people.unipmn.it/manzini/lightweight/) has useful
discussion on the history.

We tried to find out who Yuta Mori is, but had no luck.

