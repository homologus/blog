---
title: Plactic Monoid, Schubert Polynomial and Combinatorics of Words
tags: []
categories:
- blog
---
A few months back, we came across a set of informative slides from [Amy Glen,
an Australian mathematician](http://amyglen.wordpress.com/talks/), but did not
have time to dig into the details. You can click on the image to see the
slides.
<!--more-->

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/05/Capture3-300x205.png)

Finally we are starting to go through all relevant topics to fully understand
the slides. If this commentary appears like a bunch of random definitions and
links, that is what it is. We are simply making a note of all relevant links
here to go through the topics covered in them over the next 6-7 months.

\-----------------------------------------------

1\. **Marcel-Paul Schtzenberger**

[Schtzenberger](http://en.wikipedia.org/wiki/Marcel-Paul_Sch%C3%BCtzenberger)
was an eminent French scholar, who first did his PhD in medicine and then in
mathematics. Over his long career, he made very deep contributions in
combinatorics and information theory. We will come across a number of his
papers in the following links. Until the end of his life, he doubted the
evolutionary theory of Mayr and others, also known as 'modern synthesis'. In
our very personal opinions, horizontal gene transfer (reticulate evolution)
takes care of the objections he had. However, the evolution of eukaryotic
cells from prokaryotic cells is still a mystery. Dan Graur wrote a detailed
commentary on that topic.

[The Phylogeny of Everything, the Origin of Eukaryotes, and the Rules of
Taxonomy: Death to Archaea, Bacteria, and Eucarya! Long live Archaebacteria,
Eubacteria, Eukaryota, and
Prokaryota!](http://judgestarling.tumblr.com/post/79135526488/the-phylogeny-
of-everything-the-origin-of-eukaryotes)

\-----------------------------------------------

2\. **Combinatorics Books by M. Lothaire**

M. Lothaire is an eminent French mathematician, who does not exist. The
students of

Schtzenberger joined together to write books under the above pseudonym
(copying the tradition of N. Bourbaki). They have three books so far.

[Lothaire's Books](http://www-igm.univ-mlv.fr/~berstel/Lothaire/)

[Algebraic Combinatorics on Words](http://tomlr.free.fr/Math%E9matiques/Fichie
rs%20Claude/Auteurs/aaaDivers/Lothaire%20-%20Algebraic%20Combinatorics%20On%20
Words.pdf)

[Applied Combinatorics on Words](http://lipn.univ-paris13.fr/~duchamp/Books&mo
re/Lothaire/\(Encyclopedia_of_Mathematics_and_its_Applications_\)M._Lothaire-
Applied_Combinatorics_On_Words-Cambridge_University_Press\(2005\).pdf)

\-----------------------------------------------

3\. **Plactic Monoid**

What is a [monoid](http://en.wikipedia.org/wiki/Monoid)? They are groups minus
inverse property.

> In abstract algebra, a branch of mathematics, a monoid is an algebraic
structure with a single associative binary operation and an identity element.
Monoids are studied in semigroup theory as they are semigroups with identity.
Monoids occur in several branches of mathematics; for instance, they can be
regarded as categories with a single object.

The following image from [wiki page on
groups](http://en.wikipedia.org/wiki/Group_\(mathematics\)) describes all
group and group-like structures.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/05/Capture4-300x126.png)

Those interested in group theory should check out the following project, which
appears like the 'human genome project of group theory'.

[Classification of finite simple
groups](http://en.wikipedia.org/wiki/Classification_of_finite_simple_groups)

Finally, here is the definition of [plactic
monoid](http://en.wikipedia.org/wiki/Plactic_monoid) \-

> In mathematics, the plactic monoid is the monoid of all words in the
alphabet of positive integers modulo Knuth equivalence. Its elements can be
identified with semistandard Young tableaux. It was discovered by Donald Knuth
(1970) (who called it the tableau algebra), using an operation given by Craige
Schensted (1961) in his study of the longest increasing subsequence of a
permutation.

It was named the "monode plaxique" by Lascoux & Schtzenberger (1981), who
allowed any totally ordered alphabet in the definition. The etymology of the
word "plaxique" is unclear; it may refer to plate tectonics (tectonique des
plaques in French), as the action of a generator of the plactic monoid
resembles plates sliding past each other in an earthquake.

[Monoid factorisation and Schtzenberger theorem](http://en.wikipedia.org/wiki/
Sch%C3%BCtzenberger_theorem#Sch.C3.BCtzenberger_theorem)

\-----------------------------------------------

4\. **Representation theory**

[Representation theory](http://en.wikipedia.org/wiki/Representation_theory)
converts all group theory problems into linear algebra problems. Since the
later subject is well studied, the conversion helps in solving problems from
the former subject.

Conceptually it is like coordinate geometry+trigonometry, which is used to
solve geometry problem by translating them into algebraic problems. Some
mathematicians do not like solving problems in one domain by using machinery
in other domain, because often the elegance of mathematics is lost. Ivan
Niven's "Maxima and Minima without Calculus" is a fascinating book on that
topic.

[Maxima and Minima Without Calculus (Dolciani Mathematical
Expositions)](http://www.amazon.com/Without-Calculus-Dolciani-Mathematical-
Expositions/dp/088385306X)

On the other hand, Wiles solved Fermat's last theorem (a number theory
problem) by using techniques in algebraic geometry. What is good for the
gander may not be good for the goose here :)

\-----------------------------------------------

5\. **Schubert and Schur polynomial**

[Schur polynomials](http://en.wikipedia.org/wiki/Schur_polynomials) are
certain kinds of symmetric polynomials with very special properties.

[Schubert polynomials](http://en.wikipedia.org/wiki/Schubert_polynomial) are
generalization of Schur polynomials.

Relevant paper is available [here](http://igm.univ-
mlv.fr/~berstel/Mps/Travaux/A/1985-2SchubertMathPhys.pdf).

Also check -

[Combinatorial aspects of the LascouxSchutzenberger tree by David P.
Little](http://ac.els-cdn.com/S0001870802000385/1-s2.0-S0001870802000385-main.
pdf?_tid=448e4da0-d412-11e3-911f-
00000aacb35d&acdnat=1399266247_e4a7b0f655000b55a78ad78df8172021)

\-----------------------------------------------

**Where do they all fit?**

Thanks for asking. A string of concatenated characters or words is a good
example of monoids. They follow associative rule, but not any other property
of groups. Therefore, it is interesting to check their general mathematical
properties in terms of factorization.

After all, factorization of large strings is useful in parallelizing the
construction of large BWT structure, such as a large genome or large Illumina
library).

