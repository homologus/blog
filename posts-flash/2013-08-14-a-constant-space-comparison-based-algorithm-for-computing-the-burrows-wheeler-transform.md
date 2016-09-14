---
title: A Constant-Space Comparison-Based Algorithm for Computing the Burrows&ndash;Wheeler
  Transform
tags: []
categories:
- blog
---
[This is really cool
paper](http://link.springer.com/chapter/10.1007%2F978-3-642-38905-4_9) and the
only not-so-cool-part is the closed access. We guess [the king is
broke](http://en.wikipedia.org/wiki/King%27s_College_London) after fighting
too many wars. In any case, thanks to @srbehera11 and an anonymous helper, we
managed to receive the pdf copy.
<!--more-->

>

To compute BWT(Ts), suppose that BWT(Ts+1) has been already computed and
stored in the last positions of T, i.e. T[s+ 1..n? 1]. Consider the current
symbol c = T[s]: if we look at the content of T[s..n? 1], we no longer ?nd Ts,
but the symbol c followed by the permutation BWT(Ts+1) of Ts+1. Nevertheless,
we still have enough information as we will show in the proof of Theorem 1
that the position of $ inside BWT(Ts+1) is related to the rank of Ts+1 among
the su?xes Ts+1,...,Tn?1. We exploit this fact in the following steps.

1\. Find the position p of the $ in T[s+ 1..n?1]: note that p?s is the (local)
rank of the su?x Ts+1 that originally was starting at position s+ 1.

2\. Find the rank r of the su?x Ts (originally in position s) using just
symbol c. To this end, scan T[s+ 1..n?1] and count how many symbols are
strictly smaller than c and how many occurrences of c appear in T[s + 1..p]
(and add s as an o?set to obtain r).

3\. Store c into T[p] (thus replacing the $).

4\. Insert the symbol $ in T[r] by shifting T[s+ 1..r] by one position left.

So far, in the long history of BWT field, only two words have been converted
to BWT - 'MISSISSIPPI$' and 'BANANA$'. We will introduce a third one to
greatly advance the field -

Step 1: homolog.uS$ [Last two letters BWTed]

Step 2: homolog.SU$ [Last three letters BWTed]

Step 3: homologS$U. [Last four letters BWTed]

Step 4: homoloSG$U. [Last five letters BWTed]

Step 5: homolSGO$U. [Last six letters BWTed]

Step 6: homoSGO$LU. [Last seven letters BWTed]

Step 7: homSGOOL$U. [Last eight letters BWTed]

Step 8: hoSGOO$LMU. [Last nine letters BWTed]

Step 9: hSGOOOLM$U. [Last ten letters BWTed]

**Final: SGO$OOLMHU. [All letters BWTed]**

What is going on? Let us explain. At each step, we are incorporating one extra
character from the right into the BWT. To do so, places for only two
characters need to be decided - the $ and the new character at (k+1) position
from the right. The rules are simple and given in 1-4 mentioned above.

You can compare the result [with our earlier
commentary](http://www.homolog.us/blogs/blog/2011/10/03/finding-us-in-homolog-
us/), where we derived the same by sorting the full matrix. Only difference
here is that we did the calculation in constant space by deriving BWT of last
k+1 characters from BWT of last k characters. The cost is time, which you can
spend by updating twitter :)

The paper also provided C code for computing BWT (see below) and inverse BWT
(not shown here).

`

void inplaceBWT( unsigned char T[ ], int n ){

int i, p, r, s;

unsigned char c;

for ( s = n-3; s >= 0; s-- ){

c = T[ s ];

/* steps 1 and 2 */

r = s;

for ( i = s+1; T[ i ] != END_MARKER; i++ )

if ( T[ i ] <= c ) r++;

p = i;

while ( i < n )

if ( T[ i++ ] < c ) r++;

/* step 3 */

T[ p ] = c;

/* step 4 */

for ( i = s; i < r; i++ )

T[ i ] = T[ i+1 ];

T[ r ] = END_MARKER;

}

}

`

Edit.

Readers may find a comment by Jared Simpson helpful -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/08/Capture20-300x164.png)

BCR algorithm mentioned above comes from Anthony Cox of Illumina and
colleagues, and we covered it many times.

