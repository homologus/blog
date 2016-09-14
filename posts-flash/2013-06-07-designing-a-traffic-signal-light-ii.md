---
title: Designing a Traffic Signal Light - II
tags: []
categories:
- blog
---
We are going through few interesting papers, each pushing the boundaries on
short read alignment in its respective domain - namely CPU, GPU and FPGA. The
first one is [BWA-mem](http://www.homolog.us/blogs/blog/2013/05/27/bwa-mem-
heng-lis-answer-to-bowtie2/), published ([or rather
'unpublished'](http://www.homolog.us/blogs/students/2013/05/29/mapping-god-
scientifically-dishonest/)) by Heng Li. Various comparisons suggest that it is
the state of the art in CPU-based alignment. Non-believers are encouraged to
join [the food-fight at seqanswers
forum](http://seqanswers.com/forums/showthread.php?t=15200&page=5). Second one
is [Ruibang's SOAP3-dp](http://www.plosone.org/article/info%3Adoi%2F10.1371%2F
journal.pone.0065632) published in PLOS One last week. Third paper -
"[Shepard: A Fast Exact Match Short Read
Aligner](http://rcl.ece.iastate.edu/sites/default/files/papers/NelTow12A.pdf)"
- comes from an Iowa state group and claims to be the best in FPGA-based short
read alignment. We like to go into the details of all three algorithms
provided you tolerate a bit of childish fun with design of a traffic signal
light. The original question was posted in our previous commentary -
<!--more-->

[Designing a Traffic Signal
Light](http://www.homolog.us/blogs/blog/2013/05/29/designing-a-traffic-signal-
light/).

\---------------------

Adding two binary numbers -

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/06/write-
blog-300x85.png)

Circuit -

![write-blog2](http://www.homolog.us/blogs/wp-content/uploads/2013/06/write-
blog2-300x150.png)

\----------------------

Odd number of NOT gates create oscilattor.

![write-blog3](http://www.homolog.us/blogs/wp-content/uploads/2013/06/write-
blog3-300x84.png)

\----------------------

Multiple D-flip flops create ripple counter:

![write-blog4](http://www.homolog.us/blogs/wp-content/uploads/2013/06/write-
blog4-300x125.png)

![write-blog5](http://www.homolog.us/blogs/wp-content/uploads/2013/06/write-
blog5-300x254.png)

\----------------------

At last, the signal light:

![write-blog6](http://www.homolog.us/blogs/wp-content/uploads/2013/06/write-
blog6-300x233.png)

