---
title: Our Response to "Best Practices for Scientific Computing" Paper
tags: []
categories:
- blog
---
Please help us figure out [this C
code](http://www0.us.ioccc.org/2011/eastman/eastman.c) before we can take you
seriously -
<!--more-->

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/10/Capture2-237x300.png)

Jokes apart, [here](http://arxiv.org/pdf/1210.0530v1.pdf) is the **Best
Practices for Scientific Computing paper** at arxiv.org.

**Abstract:**

> Scientists spend an increasing amount of time building and using software.
However, most scientists are never taught how to do this efficiently. As a
result, many are unaware of tools and practices that would allow them to write
more reliable and maintainable code with less effort. We describe a set of
best practices for scientific software development that have solid foundations
in research and experience, and that improve scientists productivity and the
reliability of their software.

And if those best practices are too restrictive,
[here](http://www0.us.ioccc.org/years.html#2000_jarijyrki) you can get more C
codes like the one posted above.

\----------------

Here is my general criticisms of management-type papers such as the one linked
above.

**A.** It is very hard to talk about 'general software writing' practices, or 'general bioinformatics practices', because the audience is very diverse. That is why, in our earliest commentaries ([here](http://www.homolog.us/blogs/2011/07/22/a-beginners-guide-to-bioinformatics-part-i/) and [here](http://www.homolog.us/blogs/2011/07/22/a-beginners-guide-to-bioinformatics-part-ii/)), we partitioned bioinformaticians into five groups - 

a) Those using various graphical/web-based tools for their bioinformatics
analysis,

b) Those who run packaged commands from linux command line,

c) Those who do statistical/quantitative analysis of data in R, PERL or
python,

d) Those who write C/C++ codes,

e) Those who think of new algorithms.

Of course those groups overlap to some extent, but I do not think Pavel
Pevzner (group e) is losing sleep over plotting median expressions of 10
samples.

Because of wide range of need for computer in biology, it is hard to propose
common set of 'best practices'. Yes, I know that MBAs do that a lot, but...

**B.** The most useful tip for writing good software code is somehow missing. 

It is - **Identify few boundary condition for your specific application, and
test it for those boundary conditions.** That is how the errors get detected.

You wrote a genome assembler? Test it for one small gene. Or, for a genome
with all Ts. Yes, we know that there is no genome with all Ts, but computers
do not know and you do not know that they do not know.

When I started my MS, I was a good programmer with no knowledge of physics and
my professor was a physicist with no knowledge of programming. Still, no
matter how complicated my molecular simulation programs were, he could often
find out when they did not work. How? The programs were on predicting
resistance of a small molecule connected between two metal wires, and he asked
me to check what would happen, when the molecule was the same as the metal.
That simple boundary condition often caught 2/3rd of the bugs.

Most important thing to recognize though is that those boundary conditions are
domain specific, and there is no way to find a generic testing library for all
bioinformatics programs.

**C.** The section on testing reminded us of the old quote - _Quis custodiet ipsos custodes?_ [Translated in English: Who tests the text in testing section? :) ] 

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/10/Capture3-300x283.png)

