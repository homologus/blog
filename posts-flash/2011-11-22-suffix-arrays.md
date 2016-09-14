---
title: Suffix Arrays
tags:
- bowtie
- BWT
- BWA
categories:
- blog
---
If you read our commentaries on Burrows Wheeler transform (BWT)
[here](http://www.homolog.us/blogs/2011/10/03/finding-us-in-homolog-us/) and
[here](http://www.homolog.us/blogs/2011/10/05/finding-us-in-homolog-us-part-
ii/), you learned how the transform was done, but did not develop an intuitive
feel for what made Mr. Burrows and Mr. Wheeler think about the procedure. In
this post, we present an indexing technique called suffix arrays that will
lead you naturally to Burrows Wheeler transform. If you allow us to use an
analogy, you were airdropped on the top of a high mountain in our previous
method for discussing BWT, whereas today we shall slowly climb up to the top.
Both approaches have advantages and disadvantages. When you were airdropped,
you could enjoy the view from the top without any pain of climbing. The hiker,
on the other hand, gets considerable pleasure from the hike itself, and that
is what we are looking for today.
<!--more-->

We introduced the concept of [indexing](http://www.homolog.us/blogs/2011/10/17
/search-algorithm-and-indexing/) in a previous post. Today we shall explore
indexing for word search algorithms.

Suppose you are given hundreds of short words and are asked to find the ones
present in a reference text and their locations. This is essentially the
general description of the problem being solved by all short read alignmers.

**Brute Force Approach**

We shall first investigate the difficulties faced by a brute force approach.
As a simple example, let us choose the following reference text - 'Homolog.us,
Frontier in transcriptomics'.

The first word we are searching for is 'in'. The simplest algorithm starts
from the beginning of the text and compares each letter with the first letter
in the query -'i'.

Does 'H' match with 'i'? No.

Does 'o' match with 'i'? No.

Does 'm' match with 'i'? No.

The algorithm continues in this fashion and finds 'i' in 22nd location. It
compares the next letter 'n' with 23rd letter in reference, and finds a match.
The word 'in' exists in reference text in the 22nd location. The algorithm
continues with rest of the reference text and finds three more 'i's. However,
none of them match the complete word 'in'.

The second word to look for is 'to'. The algorithm again starts from 'H' and
continues with 'o', 'm', 'o', 'l' and so on. It finds 'to' to be present in
reference text in 34th location. The remaining matches with 't' do not contain
the word 'to'.

The third word is 'From'. The algorithm again goes through 'H', 'o', 'm', etc.
to find a match with F at the 13 th location. However, only the first three
letters of From match the reference text, and the search is abandoned in the
fourth letter. The word 'From' is not present in the reference text.

Imagine searching for 100 million short reads in human genome in the above
fashion. Even one walk through the genome can take several minutes in a very
fast machine. Searching for 100 million reads can take centuries. You start
your program and go take a long coffee break of one hundred years to get the
results. Nice try !!

**Improvement by Indexing**

Thinking through the above approach, you will notice one major drawback. For
each word being searched, we need to walk through the entire reference text.
Therefore, one simple improvement can dramatically cut down the search time.
Let us go back to the reference text - 'Homolog.us, Frontier in
transcriptomics', and create another array to store the locations of various
letters.

,

11

12,21,24

.

8

a

27

c

30,38

e

19

F

13

g

7

H

1

i

18,22,32,37

l

5

m

3,36

n

16,23,28

o

2,4,6,15,35

p

33

r

14,20,26,31

s

10,29,39

t

17,25,34

u

9

We can utilize this second array to reduce the search time. For every word, we
first look for the location of its first letter in the second array. Then we
search the reference text only at few locations addressed by the second array.
For the word 'in', second array lists 'i' only at locations 18, 22, 32, and 37
of reference text. So, we can compare the word at only those four locations.

Creating the second array also provides another major advantage. Suppose the
word to be looked for is 'with'. We immediately find out that the letter 'w'
does not exist in the table. So, 'with' is rejected without even going through
the reference text, whereas the brute force approach would have required us to
walk through the entire text to come to an answer.

What is the drawback of the improved algorithm? It takes extra space (RAM),
and more we want to gain on time, more RAM is needed. To understand the trade-
off between the size of the index and improvement in search speed, consider
the human genome. If you store the locations of all As, Cs, Gs and Ts, that
will not help much. Unlike the short reference text 'Homolog.us, Frontier in
transcriptomics', the genome has simply too many As, Cs, Gs and Ts. Therefore,
the index needs to save locations of longer words. Even going to 2 letter
words (AA, AC...TTs), 3 letter words (AAA, ATC, AGC, etc.) or 4 letter words
(AAAA, AAAC, etc.) is not enough. The index needs to be 8-10 nucleotides long
to be sufficiently distinct so that only few areas of the genome are searched.

**Indexes of Variable Sizes**

If we drop the notion of saving fixed sized indexes and instead make the
constraint that all indexes need to have unique location on the genome, we
essentially reach suffix array. Going back to the previous index table shown
above, we observe that the letters ' ', 'c', 'i', 'm', 'n', 'o', 'r', 's' and
't' match multiple coordinates. So, we consider two positions for those
letters to break the redundancy. That works for all letters except 'o', where
three letters are needed. The index table is sorted alphabetically based on
the words and is shown below. This is the 'suffix array' for the reference
sequence. The experts may find this approach for deriving suffix array as non-
traditional, but it is more intuitive to a beginner.

,

11

 F

12

 i

21

 n

24

.

8

a

27

cr

30

cs

30

e

19

F

13

g

7

H

1

ic

37

ie

18

in

22

ip

32

l

5

mi

36

mo

3

n

23

ns

28

nt

16

og

6

ol

4

omi

35

omo

2

on

15

p

33

r

20

ra

26

ri

31

ro

14

s,

10

s

39

sc

29

ti

17

to

34

tr

25

u

9

In the next commentary, we shall investigate how suffix array is used in word
searches and its relationship to Burrows Wheeler transform.

