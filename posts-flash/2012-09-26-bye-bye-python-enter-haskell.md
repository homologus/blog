---
title: Bye bye Python; Enter Haskell
tags: []
categories:
- blog
---
The only 'programming language' a computer understands has two 'commands' - 0
and 1. That language also happens to be the one that human programmers have
the most difficulty with, and so the need arose for human-like languages.
However, it could never be forgotten that all codes developed in human-like
abstract languages had to be translated into 0s and 1s at the end of the day.
<!--more-->

The proliferation of programming languages over the last 50 years was related
to balancing the above two aspects. At first, programs were written in
assembly language, which was nothing but Anglicized machine code. When
computers became larger and programmers felt a bit more 'wasteful', languages
like C and PASCAL came in. It took another 30 years for computers to be large
enough to allow domination of scripting languages (PERL, python, ruby, PHP)
over C and C++.

The computing hardware world went through another major transformation over
the last five years to support another upgrade in programming paradigm. It is
the introduction of many cores. The older languages like C or C++ cannot be
programmed seamlessly, while taking advantage of many cores. That is where
Haskell, a functional language, can help.

Please note that we are not saying that multi-cores cannot be programmed in
C/C++ or programmed efficiently in C/C++. Haskell will make it easy to write
scalable code without significant loss in speed. The transformation we are
suggesting is similar to the one from assembly language to C. Most programmers
knew that assembly codes were efficient, but those, who continued to write
assembly language code, did not manage to build very complex applications.

Here we will add links to few Haskell resources, if you are interested to get
started.

A. **SO Comment**: The best place to start with is to read the first comment
in [this stackoverflow exchange](http://stackoverflow.com/questions/1012573
/getting-started-with-haskell).

B. **Book 'Learn You a Haskell'**: [freely available
online](http://learnyouahaskell.com/chapters)

C. **Book ' Real World Haskell'**: [freely available
online](http://book.realworldhaskell.org/)

D. **Haskell 99 problems**: [link](http://haskell.org/haskellwiki/H-99
%3a_Ninety-Nine_Haskell_Problems)

E. **Project Euler problems**:
[link](http://projecteuler.net/index.php?section=problems) (I am starting to
think that Euler was a smart kid given how he managed to impress both
bioinformaticians and Haskell programmers. Was he from Harvard?).

F. **GHC compiler**: [Download](http://www.haskell.org/ghc/)

G. **Haskell online manual**:
[Link](http://www.haskell.org/haskellwiki/Haskell)

H. A set of 13 video lectures on functional programming:
[Link](http://channel9.msdn.com/Series/C9-Lectures-Erik-Meijer-Functional-
Programming-Fundamentals/Lecture-Series-Erik-Meijer-Functional-Programming-
Fundamentals-Chapter-1)

and last but not the least,

I.

[An introduction to Monads](http://ompldr.org/vY29zdw/All_About_Monads.pdf) !!

Enjoy !!!

\-----------------------

[Here](http://hammerprinciple.com/therighttool/items/python/haskell) is a
comparison of Python vs Haskell. Funniest response is shown below.

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/09/Capture10-300x39.png)

Speed comparison of Haskell and Python is [here](http://shootout.alioth.debian
.org/u64q/benchmark.php?test=all&lang=ghc&lang2=python3) \-

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/09/Capture23-300x182.png)

Based on my understand, Haskell programs run slightly slower than C/C++, but
often faster than PERL/python (without PyPy) in single CPU. The biggest
advantage is in how easy it is to modigy codes to take advantage of multiple
cores.

