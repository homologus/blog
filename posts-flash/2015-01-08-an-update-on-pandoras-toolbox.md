---
title: An Update on Pandora's Toolbox
tags: []
categories:
- blog
---
If you are following our developments on [Pandora's
Toolbox](http://www.homolog.us/blogs/blog/2015/01/05/introducing-pandoras-
toolbox-and-pandoras-modules/), here is an update.
<!--more-->

1\. **HMMER** \- I am using the original HMMER name after discussions with
Sean Eddy about the name trademark. Many thanks to him for clarifying the
issues.

2\. **Citation** \- In the [github page](https://github.com/homologus
/Pandoras-Toolbox), I updated the README file to clarify that users should
cite the individual authors and NOT Pandora's toolbox. I am working on the
README file to put together the list of proper citations, but still some have
work to do.

3\. **New Programs** \- I added tophat and cufflinks to the previous list of
programs. Initially, I had difficulty compiling them, but now I am finally
successful to fully compile each program in my list. Sailfish was a difficult
one, but with help from Rob Patro, I managed to compile that as well. Those
changes have not been pushed to github yet.

4\. Three programs are absolutely amazing - BWA, DALIGNER and HMMER. They
compile, no matter which machine I take them to. C++ and boost-based programs,
on the other hand, are giving me the most difficulties.

5\. Now that I have the basic structure ready, I am able to fill up holes here
and there by adding extra codes. Here is a good example.

One of my collaborators has been asking about programs to assemble a very
large genome (>30 gigabases) and mentioned that he was running out memory in
his terabyte RAM machine. That problem can be easily solved with KMC+bcalm.
So, I wrote a short modifier (kmc_dump_bcalm) that produces kmc output in a
format that can be directly fed directly to bcalm. Based on the numbers I have
seen, the first and memory intensive step of assembly can be done with only
20-30 gigabytes of RAM.

I like to put together a short manual describing each program, and how they
can be used in combination with each other to solve problems efficiently.
There are so many really good and memory-efficient programs scattered around
at all places that it is a shame that people are still struggling with large
libraries and high RAM machines.

I thought about why the efficient programs are not merging with each other and
realized that the problem is with credits. Firstly, individual researchers
like to develop their own programs and get cited for funding. At the next
higher level, those researchers belong to large organizations and those large
organizations like to promote their own set of programs. A researcher from
Broad institute is not going to give presentation on why BGI's or EBI's
assemblers are better than theirs and vice versa. Citation, money and
hierarchy are stopping us from mixing and matching programs to the fullest
extent.

That is why I thought it would worthwhile to try a different model and see
whether that helps the community. So, once again, I urge you to NOT cite
Pandora's toolbox. Please cite the individual authors of the programs instead.
This is irrespective of my minor modifications made to the code base.

