---
title: Will I Use Kallisto? Definitely, Most Likely and Never
tags: []
categories:
- blog
---
[Kallisto](http://pachterlab.github.io/kallisto/) is an efficient program for
RNAseq quantification [published by Lior Pachter's
lab](https://liorpachter.wordpress.com/2015/05/10/near-optimal-rna-seq-
quantification-with-kallisto/). We wrote about it in ["Lightweight Algorithms
for RNAseq Expression Analysis Sailfish, Kallisto and
Salmon"](http://www.homolog.us/blogs/blog/2015/05/14/lightweight-algorithms-
for-rnaseq-expression-analysis-sailfish-kallisto-and-salmon/) and also pointed
out its [unconventional license](http://www.homolog.us/blogs/blog/2015/05/18
/pachters-kallisto-comes-with-unconventional-license/). The issue of non-
MIT/GPL license seems to have created a twitter storm, but speaking of
'Kallisto', we need to remember that the word refers to three aspects coming
in one package -
<!--more-->

**i)Kallisto as an intellectual contribution in algorithm development**

RSEM, the previously used algorithm for RNAseq quantification, was alignment-
based and took days to weeks to perform simple analysis. Most likely the
expectation minimization step took too long to converge. As an alternative,
Patro and Kingsford developed Sailfish and it was huge improvement in terms of
time performance at some cost of accuracy. Kallisto recovers the lost accuracy
of RSEM, but keeps the time performance of Sailfish. That is an important
contribution in algorithm worthy of getting credit.

**ii)Kallisto as high quality code with open access**

Pll Melsted, who led the code development, is an expert in writing
bioinformatics code, and you can see the quality in Kallisto. Of course, you
can see it only because the code is available as open source.

**iii)Kallisto as a business model**

As we mentioned, Kallisto comes with non-GPL, non-MIT license.

\-------------------------------------------------

**Will you use it?**

On point (i) ("Kallisto as an intellectual contribution in algorithm
development"), we will definitely use Kallisto, because good algorithms are
hard to say no to.

On point (ii) ("Kallisto as high quality code with open access"), we will most
likely use Kallisto, until someone else develops high quality alternative.
Maybe Patro's Salmon is already there.

On point (iii) ("Kallisto as a business model"), we will never use Kallisto
codes to build or distribute a larger library, because it corrupts the
licenses of all other programs. A good example of that corrupting effect is
Kallisto code itself. You can see that it reused some libraries distributed by
Heng Li under MIT license, but the entire package has a stricter license.

\--------------------------------------------------

**What's the alternative for (iii)?**

Well, two things can happen.

Maybe the algorithm is so complex, Pll Melsted's code is so good and
Bray/Pimentel/Melsted/Pachter spend so much time in incorporating new
algorithmic modifications and versions that it is impossible to create an
alternative. Then everyone should suck up and bow to Kallisto's authors. After
all, the largest user base of the program lives in the universities and will
not have to pay for it anyway.

The other extreme is that the program becomes a huge commercial success even
though it is easy to reproduce by carefully studying and the authors do not
make any update. In that case, someone will think that its license is a lousy
deal, write a different (ii) ("high quality code with open access") based on
Kallisto algorithm and distribute under MIT/BSD.

Let us wait to determine which approximate path the users take.

