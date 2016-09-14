---
title: How Sponges will Take over the World
tags: []
categories:
- blog
---
![](http://sponge.noekeon.org/Sponge_cwilso.jpg)
<!--more-->

This commentary is about different kind of sponge than the one in the figure.
We are talking about [sponge
functions](http://en.wikipedia.org/wiki/Sponge_function).

![](http://upload.wikimedia.org/wikipedia/commons/thumb/7/70/SpongeConstructio
n.svg/300px-SpongeConstruction.svg.png)

> A sponge function is built from three components:

a state memory, S, containing b bits,

a function, f, of fixed length that permutes or transforms the state memory

a padding function P

The state memory is divided into two sections, R of size r bits and C of size
c = b - r bits. The parameter r is called the bitrate and c is the capacity.

The padding function appends enough bits to the input string so that the
length of the padded input is a whole multiple of the bitrate, r. The padded
input can thus be broken into r-bit blocks.

The sponge function operates as follows:

The state S is initialized to zero

The input string is padded

The first r-bit block of padded input is XORed with R.

S is replaced by f(S)

The next r-bit block of padded input (if any) is XORed with R.

S is replaced by f(S)

The process is repeated until all the blocks of the padded input string are
used up ("absorbed" in the sponge metaphor).

The sponge function output is now ready to be produced ("squeezed out") as
follows

The R portion of the state memory is the first r bits of output

If more output bits are desired, S is replaced by f(S)

The R portion of the state memory is the next r bits of output

The process is repeated until the desired number of output bits are produced.

Why are they important? As it appears, Keccak, a cryptographic hash function
developed based on sponge functions, won the NIST competition to [become
nominated as SHA-3](http://en.wikipedia.org/wiki/SHA-3). Part of their success
was related to being hardware friendly in design.

> The authors claim 12.5 cycles per byte[5] on an Intel Core 2 CPU. However,
in hardware implementations it is notably faster than all other finalists.

Useful papers:

[On the Indi?erentiability of the Sponge
Construction](http://www.iacr.org/archive/eurocrypt2008/49650180/49650180.pdf)

[A Keyed Sponge Construction with Pseudorandomness in the Standard Model](http
://csrc.nist.gov/groups/ST/hash/sha-3/Round3/March2012/documents/papers/CHANG_
paper.pdf)

