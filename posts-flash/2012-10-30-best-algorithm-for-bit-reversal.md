---
title: Best Algorithm for Bit Reversal
tags: []
categories:
- blog
---
We came across a fantastic response of a question at stockoverflow that
readers may like to take a look at.
<!--more-->

[Here is the question.](http://stackoverflow.com/questions/746171/best-
algorithm-for-bit-reversal-from-msb-lsb-to-lsb-msb-in-c)

> What is the best algorithm to achieve the following:

0010 0000 => 0000 0100

The conversion is from MSB->LSB to LSB->MSB. All bits must be reversed; that
is, this is not endianness-swapping.

Please take a look at the first response [in this
link](http://stackoverflow.com/questions/746171/best-algorithm-for-bit-
reversal-from-msb-lsb-to-lsb-msb-in-c).

>

NOTE: All algorithms below are in C, but should be portable to your language
of choice (just don't look at me when they're not as fast :)

Options

Low Memory (32-bit int, 32-bit machine)(from here):

The answer is relevant, if you are trying to find optimal way to determine
reverse complement of a nucleotide sequence represented in binary.

If you want a 'crazy looking' algorithm for for bit reversal, [please try
this](http://stackoverflow.com/questions/8492028/what-does-this-actually-do-
crazy-c-function?lq=1) \-

`

void swapit(unsigned char *msg, int length) {

for(;length>0;length--, msg++) {

*msg = ((*msg * 0x0802LU & 0x22110LU) | 

(*msg * 0x8020LU & 0x88440LU)) *

0x10101LU >> 16;

}

}

`

