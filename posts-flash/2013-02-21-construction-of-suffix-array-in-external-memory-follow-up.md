---
title: 'Construction of Suffix Array in External Memory - Follow Up '
tags: []
categories:
- blog
---
Many short-read alignment programs (BWA, Bowtie, SOAP2) use suffix arrays to
hold indexed reference genome, because suffix arrays provide savings in
memory. In case of human genome, BWT-indexed genome can be loaded with less
than 4 GB RAM. However, construction of suffix arrays is not so memory
efficient and can take lot more than 4GB of RAM for human genome. Few weeks
back, [we covered the state-of-the-art
algorithm](http://www.homolog.us/blogs/2013/01/28/on-constructing-suffix-
arrays-and-lcp-arrays-in-external-memory/) from Timo Bergmann and colleagues
on constructing suffix arrays and LCP arrays in external memory. Although Dr.
Bergmann's website provides excellent information on his algorithm with paper,
slides and code, we did not understand few parts of the implementation. We
sent an email to Dr. Bergmann with our questions and he graciously replied
with helpful comments. We are sharing the response for our readers in case
they get stuck where we did.
<!--more-->

\---------------------------

Question:

_Getting back to you algorithm, I understand SA-IS very well and am trying to
figure out the difference in your implementation. Let us say, you have a
massive file in the hard-disk that you want to construct Suffix array of. SA-
IS goes through the array in memory, and finds locations of S*. Instead, you
are reading chunks of it from end to beginning, and creating pointers to
locations of S*, right?

Q1. How are you storing those pointers? In disk? In memory?

Q2. In the next step, I presume you are running some kind of radix sort on the
sub-words beginning from S* elements. Are you rearranging the pointers in
memory based on reading the letters in disk? Does that need many rounds of
random disk access for every S* and every radix position? SA-IS algorithm did
not use this sorting step and instead placed S* elements in their respective
buckets._

Dr. Bergmann:

**Answers to Q1+2: Goal of the the first part it just to order all S*-substrings globally. Thus we read a portion of them into memory, sort them, write them to EM. Repeat until done. Then merge them, (reading Theta(M/B) sorted streams,) yielding a stream of sorted S*-substrings. No pointers are involved; pointers dont work in EM. In the code there are the classes "Substring" and "SubstringPtr". The Ptr class is used to sort all S*-substring within the currently loaded portion of the input. 

Only remaining problem are "long" (> B) S*-strings. These, however, can be
split basically arbitrarily.

SA-IS does not explicity sort the S*-substrings, that is true. It does
however, sorting them implicitly in it's first step: by putting the
S*-substrings into the buckets in string order and performing the two inducing
sweeps, it implicitly sorts S*-substrings. Actually that's the only purpose of
the first pair of sweeps.

SA-DS does explicit radix sorting. That is similar to was we do.**

Question:

_Q3. If you have suffix arrays or Burrows Wheeler transform constructed for
two very large files, do you know any easy way to merge them?

_

Dr. Bergmann:

**No I don't think it can be done efficiently. The best ideas about merging are already used in bwtdisk. 

I remember that to merge SA_1 and SA_2 of T_1 and T_2 efficiently in RAM you
have to search for the position of each longer suffix "s + T_2" in the SA_2
with s being a suffix of T_1 (the search can be done incrementally using
backwards search). I cant remember where I read that idea atm.**

