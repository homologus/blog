---
title: Skip Lists and Other Efficient Data Structures
tags: []
categories:
- blog
---
If you are planning to store large and sparse tables efficiently, skip list
could be an efficient solution. [Titus Brown
says](http://ivory.idyll.org/blog/2013-pycon-awesome-big-data-algorithms-
talk.html) he will implement it, if someone puts a gun on his head. We would
rather call 911 and Sebastien says he will prefer few other data structures -
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/03/Capture9-300x55.png)

![](http://upload.wikimedia.org/wikipedia/commons/thumb/8/86/Skip_list.svg
/470px-Skip_list.svg.png)

[Wikipedia page on skip list](http://en.wikipedia.org/wiki/File:Skip_list.svg)
provides good explanation of how it works.

> A skip list is a data structure for storing a sorted list of items using a
hierarchy of linked lists that connect increasingly sparse subsequences of the
items. These auxiliary lists allow item lookup with efficiency comparable to
balanced binary search trees (that is, with number of probes proportional to
log n instead of n).

If that is not enough, please try this video (h/t: @sebhtml)

<iframe width="560" height="315" src="http://www.youtube.com/embed/eIuQ07NQ5fM" frameborder="0"> </iframe>

Other relevant links -

[An Article by John Shipman](http://infohost.nmt.edu/tcc/help/lang/python/exam
ples/pyskip/pyskip.pdf)

[Original article of Bill
Pugh](ftp://ftp.cs.umd.edu/pub/skipLists/skiplists.pdf)

And do not forget Titus' talk linked at the top of the commentary.

