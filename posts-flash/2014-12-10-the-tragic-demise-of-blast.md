---
title: The Tragic Demise of BLAST
tags: []
categories:
- blog
---
BLAST is one of the most well-known bioinformatics programs. In fact, if I
remove 'one of' from the previous sentence, that will not be a mistake. The
scientists developing it received numerous well-deserved awards. For early
history of how the program was written, please check the blog post - [Once
upon a BLAST ](http://blog.thegrandlocus.com/2014/06/once-upon-a-blast).
<!--more-->

> Only the successful hypotheses and the successful experiments are mentioned
in the text a small minority and the painful intellectual labor behind
discoveries is omitted altogether. Time is precious, and who wants to read
endless failure stories? Point well taken. But this unspoken academic pact has
sealed what I call the curse of research. In simple words, the curse is that
by putting all the emphasis on the results, researchers become blind to the
research process because they never discuss it. How to carry out good
research? How to discover things? These are the questions that nobody raises
(well, almost nobody).

\-------------------------------------

<iframe width="560" height="315" src="http://www.youtube.com/embed/uAsV5-Hv-7U" frameborder="0"> </iframe>


But that is all history from early 1990s. What most researchers do not know is
that BLAST is dying at present in the hand of NCBI. It is not dying due to
lack of funding, but from over-funding. Early innovators have all left and God
knows who has taken over.

Last week, I downloaded the source codes of several bioinformatics programs we
use frequently - BLAST, BWA, samtools, SOAPdenovo2, Minia, Trinity, KMC2,
SPAdes, DAZZLER, etc. - and compiled each of them. NCBI BLAST turned out to be
THE worst among all of them.

Here are the specific complaints -

(i) BLAST compiled to executable directory (ReleaseMT) of size ~890MB ! Why
would an aligner need almost 1GB of space? For comparison, bwa compiles to
only 1.4MB.

(ii) Configure and make of BLAST took over one hour in a reasonably high-end
server. BWA compiled in exactly 12 seconds.

(iii) The BLAST executable directory seemed to have all kinds of
'sophisticated' modules, including unit tests and other junk. That is all fine
and dandy, except (see next point) -

(iii) After one hour of waiting and getting my directory filled, I desperately
looked for a 'make clean', but could not find such option. Every other program
had 'make clean' to help me get back to the ground state. Why not BLAST?

If BLAST gets any more funding, it will turn into Obamacare website software
and stop working altogether. NCBI should urgently place BLAST into github,
start derivative projects (aka wasting money) under new names. BLAST does not
need any further development and definitely no more funding to destroy it.

