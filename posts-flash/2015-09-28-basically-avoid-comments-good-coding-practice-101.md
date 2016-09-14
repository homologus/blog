---
title: '"Basically, Avoid Comments" (Good Coding Practice 101)'
tags: []
categories:
- blog
---
"Add plenty of comments" - is the universal advice you find in books and
tutorials related to computer programming. The idea is so ingrained in the
minds of programmers that they often apologize before sharing sparsely
commented code. Therefore, we were surprised to find the [unconventional
suggestion of being sparse with
comments](http://www.lysator.liu.se/c/pikestyle.html). At the bottom, I am
adding couple of videos related to the latest work of the author of the text.
<!--more-->

>

**Comments**

A delicate matter, requiring taste and judgement. I tend to err on the side of
eliminating comments, for several reasons. First, if the code is clear, and
uses good type names and variable names, it should explain itself. Second,
comments aren't checked by the compiler, so there is no guarantee they're
right, especially after the code is modified. A misleading comment can be very
confusing. Third, the issue of typography: comments clutter code.

But I do comment sometimes. Almost exclusively, I use them as an introduction
to what follows. Examples: explaining the use of global variables and types
(the one thing I always comment in large programs); as an introduction to an
unusual or critical procedure; or to mark off sections of a large computation.

There is a famously bad comment style:

`i=i+1; /* Add one to i */`

and there are worse ways to do it:

`

/**********************************

* * 

* Add one to i * 

* * 

**********************************/ 

i=i+1;`

Don't laugh now, wait until you see it in real life.

Avoid cute typography in comments, avoid big blocks of comments except perhaps
before vital sections like the declaration of the central data structure
(comments on data are usually much more helpful than on algorithms);
basically, avoid comments. **If your code needs a comment to be understood, it
would be better to rewrite it so it's easier to understand.** Which brings us
to -

<iframe width="560" height="315" src="http://www.youtube.com/embed/p9VUCp98ay4" frameborder="0"> </iframe>
<iframe width="560" height="315" src="http://www.youtube.com/embed/fc25ihfXhbg" frameborder="0"> </iframe>

