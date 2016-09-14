---
title: Mapping Algorithms - How They all Arrived
tags: []
categories:
- blog
---
We have been polishing up the [tutorials on alignment
programs](http://www.homolog.us/Tutorials/index.php?p=1.2&s=6) and wanted to
share few ideas.
<!--more-->

[This page](http://wwwdev.ebi.ac.uk/fg/hts_mappers/) shows an enormous
explosion of the number of available mappers over the last five years.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture8-300x250.png)

When you go into their codes and algorithms ([we have a section covering most
popular programs](http://www.homolog.us/Tutorials/index.php?p=1.2&s=6)), you
see that they mostly fall into handful of broad categories. Those categories
are best presented in Mark Chaisson's informative figure from BLASR paper.

![](http://www.homolog.us/Tutorials/Tut-Img/Set6/1471-2105-13-238-1.jpg)

It is also important to note that time-wise, nodes in each branch appeared
almost together and their development was as much the result of needs from
biologists as the non-biological development in computer science or electrical
engineering. For example, MUMmer, AVID, etc. were all released after 1998,
when the suffix array sub-field of computer science matured enough. SSAHA
utilized the availability of large amount of RAM in a box, not unlike what
SOAPdenovo assembler did 8-9 years later at a bigger scale to assemble the
panda genome. Even though Burrows Wheeler transform was published in 1994, it
could not be used in search programs until Paolo Ferragina and Giovanni
Manzini showed a way in their 2000 and 2005 seminal papers.

Hopefully, you will find all those discussions useful [in our tutorial
section](http://www.homolog.us/Tutorials/index.php?p=2.1&s=6). We will
continue to improve them.

