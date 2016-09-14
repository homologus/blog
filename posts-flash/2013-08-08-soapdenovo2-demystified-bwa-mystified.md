---
title: SOAPdenovo2 Demystified, BWA Mystified
tags: []
categories:
- blog
---
In January and February, we went over the code of SOAPdenovo2 genome
assembler, and discussed in a number of commentaries.
<!--more-->

[Our First Look at SOAPdenovo2 Source
Code](http://www.homolog.us/blogs/blog/2012/12/28/our-first-look-at-
soapdenovo2-source-code/)

[SOAPdenovo2 Demystified part
1](http://www.homolog.us/blogs/blog/2013/01/05/soapdenovo2-demystified-
part-1/)

[SOAPdenovo2 Demystified part
(a)](http://www.homolog.us/blogs/blog/2013/01/05/soapdenovo2-demystified-
part-a/)

[SOAPdenovo2 Demystified part (b) [multi-thread
implementations]](http://www.homolog.us/blogs/blog/2013/01/27/soapdenovo2
-demystified-part-b-multi-thread-implementations/)

[More SOAPdenovo2 Commentaries Will Come in
February](http://www.homolog.us/blogs/blog/2013/01/31/more-soapdenovo2
-commentaries-will-come-in-february/)

[SOAPdenovo2 Demystified A Rough Guideline of Functionality](http://www.homolo
g.us/blogs/blog/2013/02/05/soapdenovo2-demystified-a-rough-guideline-of-
functionality/)

Analyzing code written by someone else is not fun. In fact, analyzing own code
is not fun, if it is in PERL. Thanks to Ryan Chikhi, the author of Minia
assembler, we decided to place the SOAPdenovo2 code in wiki. Both of us were
interested in the scaffolding algorithm, and Rayan helped us figure out the
major blocks of scaffolder in SOAPdenovo2.

Today we added a new feature to the wiki page of
[SOAPdenovo2](http://homolog.us/wiki1/index.php?title=SOAPdenovo2). This is
based on a script that goes over all code files and generates dependencies
between functions in wiki format. We then upload those dependencies on the
wiki page to share with you. As an example, when you click on 'main.c' in
SOAPdenovo, the wiki page shows all functions being called and the files they
are in. Also the hyperlinks work. So, you can click on those functions to get
to the wiki section for the called function (note: the following image will
not work. You need to try in the [actual
wiki](http://homolog.us/wiki1/index.php?title=SOAPdenovo2)).

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture14.png)

To show you the usefulness of this new script, we also generated similar wiki
page for [BWA](http://homolog.us/wiki1/index.php?title=BWA). Recently, we went
through the BWA code to learn how BWA-MEM works and posted about it in a blog
commentary.

[Digging into BWA-mem Code](http://www.homolog.us/blogs/blog/2013/06/29/bwa-
code/)

The above is not panacea regarding figuring out the code and the wiki
generation script itself is not faultless, but we hope it would help you
navigate through the codes better. The BWA wiki page has no annotation apart
from the links between functions, but we can now start putting text in between
and create references for the code that others can use in their teaching or
research. At the end of the day (long summer one in Seattle :)), we like to
combine those wiki code analysis pages with the Tutorial section so that those
learning bioinformatics can do it by seeing the latest codes [from yet-to-be-
published papers](http://www.homolog.us/blogs/students/2013/05/29/mapping-god-
scientifically-dishonest/) and get to the frontier of research.

