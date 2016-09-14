---
title: The Entire World of Bit Twiddling Hacks
tags: []
categories:
- blog
---
Several months back, we posted link to Stanford bit twiddling website in
[Fastest Way to Reverse Complement a
Sequence](http://www.homolog.us/blogs/blog/2013/05/10/fastest-way-to-reverse-
complement-a-sequence/). Now thanks to ?@maxal6, we found many other useful
ones. Links to all are posted below.
<!--more-->

**1\. [Stanford bit twiddling hacks - Sean Eron Anderson](http://graphics.stanford.edu/~seander/bithacks.html)**

> Contents

About the operation counting methodology

Compute the sign of an integer

Detect if two integers have opposite signs

Compute the integer absolute value (abs) without branching

Compute the minimum (min) or maximum (max) of two integers without branching

Determining if an integer is a power of 2

Sign extending

Sign extending from a constant bit-width

Sign extending from a variable bit-width

Sign extending from a variable bit-width in 3 operations

Conditionally set or clear bits without branching

Conditionally negate a value without branching

Merge bits from two values according to a mask

Counting bits set

Counting bits set, naive way

Counting bits set by lookup table

Counting bits set, Brian Kernighan's way

Counting bits set in 14, 24, or 32-bit words using 64-bit instructions

Counting bits set, in parallel

Count bits set (rank) from the most-significant bit upto a given position

Select the bit position (from the most-significant bit) with the given count
(rank)

Computing parity (1 if an odd number of bits set, 0 otherwise)

Compute parity of a word the naive way

Compute parity by lookup table

Compute parity of a byte using 64-bit multiply and modulus division

Compute parity of word with a multiply

Compute parity in parallel

Swapping Values

Swapping values with subtraction and addition

Swapping values with XOR

Swapping individual bits with XOR

Reversing bit sequences

Reverse bits the obvious way

Reverse bits in word by lookup table

Reverse the bits in a byte with 3 operations (64-bit multiply and modulus
division)

Reverse the bits in a byte with 4 operations (64-bit multiply, no division)

Reverse the bits in a byte with 7 operations (no 64-bit, only 32)

Reverse an N-bit quantity in parallel with 5 * lg(N) operations

Modulus division (aka computing remainders)

Computing modulus division by 1 << s without a division operation (obvious)

Computing modulus division by (1 << s) - 1 without a division operation

Computing modulus division by (1 << s) - 1 in parallel without a division
operation

Finding integer log base 2 of an integer (aka the position of the highest bit
set)

Find the log base 2 of an integer with the MSB N set in O(N) operations (the
obvious way)

Find the integer log base 2 of an integer with an 64-bit IEEE float

Find the log base 2 of an integer with a lookup table

Find the log base 2 of an N-bit integer in O(lg(N)) operations

Find the log base 2 of an N-bit integer in O(lg(N)) operations with multiply
and lookup

Find integer log base 10 of an integer

Find integer log base 10 of an integer the obvious way

Find integer log base 2 of a 32-bit IEEE float

Find integer log base 2 of the pow(2, r)-root of a 32-bit IEEE float (for
unsigned integer r)

Counting consecutive trailing zero bits (or finding bit indices)

Count the consecutive zero bits (trailing) on the right linearly

Count the consecutive zero bits (trailing) on the right in parallel

Count the consecutive zero bits (trailing) on the right by binary search

Count the consecutive zero bits (trailing) on the right by casting to a float

Count the consecutive zero bits (trailing) on the right with modulus division
and lookup

Count the consecutive zero bits (trailing) on the right with multiply and
lookup

Round up to the next highest power of 2 by float casting

Round up to the next highest power of 2

Interleaving bits (aka computing Morton Numbers)

Interleave bits the obvious way

Interleave bits by table lookup

Interleave bits with 64-bit multiply

Interleave bits by Binary Magic Numbers

Testing for ranges of bytes in a word (and counting occurances found)

Determine if a word has a zero byte

Determine if a word has a byte equal to n

Determine if a word has byte less than n

Determine if a word has a byte greater than n

Determine if a word has a byte between m and n

Compute the lexicographically next bit permutation

**2\. [The Aggregate Magic Algorithms](http://aggregate.org/MAGIC/)**

> Absolute Value of a Float

Alignment of Pointers

Average of Integers

Bit Reversal

Comparison of Float Values

Comparison to Mask Conversion

Divide Rounding

Dual-Linked List with One Pointer Field

GPU Any

GPU SyncBlocks

Gray Code Conversion

Integer Constant Multiply

Integer Minimum or Maximum

Integer Power

Integer Selection

Is Power of 2

Leading Zero Count

Least Significant 1 Bit

Log2 of an Integer

Next Largest Power of 2

Most Significant 1 Bit

Natural Data Type Precision Conversions

Polynomials

Population Count (Ones Count)

Same Within Tolerance

Shift-and-Add Optimization

Sign Extension

Swap Values Without a Temporary

SIMD Within A Register (SWAR) Operations

Trailing Zero Count

**3\. [The Assembly gems page](http://www.df.lth.se/~john_e/fr_gems.html)**

> x86 gems

4x4 by 4x1 matrix multiply

63 bit CRC

Absoulte Value of

Add with 255 saturation

Aligned Fill

Bit Block Inversion

Bit Transposition algorithm

BSWAP with 16-bit registers

CodeAlign - Align your code

Convert hex to ASCII

Converting DX:AX into a base 10 string

Copy Zero Flag to Carry Flag

Copying data using the FPU

Disable the Cache(s)

Dividing 64-bit unsigned integers

Dividing signed integers by powers of 2

Doing a NOP

Exchange two values

Fast Float to Int

Fast Nibble swap

Fast strlen()

Filling a register with the Carry Flag

Find common divisor

Find minimum of two unsigned values

Get Parity of 32-bit word

Halt - the loop

Hadamard Transform in MMX

IF using AND

Inverse squareroot

LEA a power command

MOVS with SI=-X, DI=+X

Negate multiple-word numbers

Penalties on the 486

Performance monitoring

Population count of a 32-bit register

Pseudo Random number generator

Quad-precision shift

Quad Adders

Reversing bit order

Round signed integers

SALC - Set AL on Carry

Shifting + rounding upwards

Shifting bit arrays

Sinus Generator - 40 bytes

Small bubble sort

Smaller loops

Snippets from Ramblings in Realtime

Square root < 20 cycles

Testing for zero

The ADC-Gem

ulong2ascii

x86 Mnemonic Replacements

Emulate Bit scan instructions

Emulate BSF instruction

Fast BSF replacement

Remove shift by one latency

Replace Bit scan instructions

Replace MOVSX/MOVZX

Usage of JCXZ/JCXNZ

PC Platform Gems

A BIOS delay

Flat Real Mode

Flat Real Mode with EMM

Writing a string

Writing a two-digit number

PC VGA Gems

DRAMs Speed Up/Booster

Drawing pixels

Palette Programming

PC Tiny Programs

15-byte Dump Meg to STDOUT

20-byte Starfield

56-byte Sierpinski's Triangle Generator

61-byte Mandelbrot generator

65-byte Life Simulator

78-byte Fade screen

79-byte Copper bar x 3

80-byte Pi calculator

84-byte Sample player

122-byte Quality fire

Motorola Gems

Absoulte Value of

Clear / Fill memory fast

Insert sort

Jump tables

Optimize for MC68k CPUs

4\. [JJ's Source code for low level binary
functions](http://jjj.de/bitwizardry/bitwizardrypage.html)

> bitasm.h: conditionally include inline asm versions of various functions.

Define BITS_PER_LONG:

Many of the files #include

bitsperlong.h which #defines BITS_PER_LONG according to sizeof(long).

The type 'unsigned long' is abbreviated 'ulong' throughout, this is done in
fxttypes.h via

typedef unsigned long ulong;

Inline assembler (for i386 and AMD64):

bitasm-i386.h: i386 inline asm.

bitasm-amd64.h: AMD64 inline asm.

Combinatorial routines:

bitsubset.h: generate all bit-subsets of a word.

bitsubset-gray.h: all bit-subsets of a word, Gray code order.

bitlex.h: generate all bit sets in (subset-)lex order.

bit-sl-gray.h: Gray code corresponding to subset-lex order (SL-Gray order).

bin-to-sl-gray.h: conversion from binary to SL-Gray order.

bitcombcolex.h: generate all bit-combinations in colex order.

bitcombcolex.h: generate all bit-combinations in colex order.

bitcombminchange.h: generate all bit-combinations in minimal-change order
(Gray code).

fibrep-subset-lexrev.h: Fibonacci representations in subset-lex order.

bitfibgray: Gray code for the Fibonacci words.

bit-rll2.h: run length limited (RLL) words and Gray code for the Fibonacci
words.

parenwords.h: determine whether binary word corresponds to a well-formed
parenthesizing.

bit-necklace.h: generate all binary necklaces.

bitcombshifts.h: generate all combinations in shifts order.

thue-morse.h: Thue-Morse sequence.

grsnegative.h: whether Golay-Rudin-Shapiro sequence negative at an index.

Arithmetic and representation in non-standard bases:

average.h: average of two integers avoiding overflow.

evenodd.h: next_even(), next_odd() etc.

negbin.h: conversion from and to radix -2.

radix-m4.h: conversion from and to radix -4.

radix-2i.h: conversion from and to the complex radix (2*i).

radix-m1pi.h: conversion from and to the complex radix (-1+i).

bin2naf.h: non-adjacent form: sparse signed binary representation.

fibrep.h: Fibonacci representations.

bitsequency.h: generate all words with given number of edges.

bit2adic.h: 2-adic inverse and square root.

Space-filling curves:

hilbert.h: 1dim coord. to 2dim Hilbert coord.

zorder.h: 1dim coord. to 2dim/3dim space filling curve, Z-order.

bit-paper-fold.h: paper-folding sequence, also turns of the dragon curve.

bit-dragon3.h: turns of the terdragon curve.

bit-dragon-r4.h: turns of the R4-dragon curve.

bit-dragon-r5.h: turns of the R5-dragon curve.

bit-dragon-r7.h: turns of the R7-dragon curve.

bit-dragon-r9.h: turns of the R9-dragon curve.

bit-dragon-r13.h: turns of the R13-dragon curve.

Functions about cyclic rotations, necklaces, and Lyndon words:

bitrotate.h: rotating words.

bit-necklace.h: generate all binary necklaces.

bitcyclic-minmax.h: min and max among bitwise rotations.

bitcyclic-period.h: periodicity of bitwise rotations.

bitcyclic-dist.h: distance among bitwise rotations.

bitcyclic-match.h: matching bitwise rotations.

bitcyclic-xor.h: rotate-xor operation and its inverse.

bitperiodic.h: creating a periodic word.

Gray code, parity, and invertible transformations:

graycode.h: graycode and its inverse.

parity.h: parity.

revgraycode.h: reversed Gray code and its inverse.

graypower.h: Gray code powered.

bittransforms.h: invertible transforms of binary words: blue-, yellow-, cyan-,
and red code.

blue-fixed-points.h: fixed points fo the blue code.

bitxtransforms.h: invertible transforms Kronecker-powered.

Cyclic Redundancy Check (CRC):

crc64.h: 64 bit CRC .

crc32.h: 32 bit CRC.

tcrc64.h: CRC with lookup table, 64 bit.

pcrc64.h: parallel CRC, 64 bit.

Mixing colors (8-bit RGB channels):

colormix.h: functions that add/average/multiply/mix color channels.

colormixp.h: versions of some of the above funcs that are correct to the last
bit.

colormix-fl.h: color manipulation with floating point scaling.

Permutations of bits:

bitzip.h: even/odd bits to/from low/high bits.

bitzip-pairs.h: even/odd bits to/from low/high bits.

bitbutterfly.h: auxiliary routine for bit-zip.

bitswap.h: swapping groups of bits.

revbin.h: reversing the order of bits in a word.

revbin-upd.h: counting in bit-reversed order.

bitgather.h: bit gather/scatter.

bitseparate.h: separate bits according to a mask.

Isolation of low or high bits and blocks:

bitlow.h: functions that isolate/find the lowest set bit.

bitlow-edge.h: create 10 or 01 edge at the lowest set bit.

bithigh.h: functions that isolate/find the highest set bit.

bithigh-edge.h: create 10 or 01 edge at the highest set bit.

bit-isolate.h: isolation of bits/blocks at low and high end, and at 0/1 and
1/0 transitions.

bit2pow.h: functions like floor(log2()).

bitldeq.h: comparing base-2 logarithms of two words.

All the rest (low level functions):

bitcount.h: population count: counting the bits in a word.

bitblock.h: generating a bit block.

bitsubsetq.h: return whether a word is a bit-subset of another word.

ith-one-idx.h: index of the i-th set bit in a word.

bittest.h: testing and changing bits of a word.

bitcopy.h: copying bits of a word.

branchless.h: code that avoids branches.

zerobyte.h: finding zero bytes in a word.

tinyfactors.h: determining whether d divides x for d,x<BITS_PER_LONG.

cswap.h: conditional swap.

**5\. Other sources shared by University of Kentucky site -**

* [HAKMEM](http://www.inwap.com/pdp10/hbaker/hakmem/hakmem.html)

_a collection of mostly low-level tricks and

otherwise interesting ideas, some quite old_

* [Bit Twiddling Hacks](http://graphics.stanford.edu/~seander/bithacks.html)

_a page full of tricks very similar in spirit to those here_

* [AMD Athlon Processor x86 Code Optimization Guide](http://www.amd.com/us-en/assets/content_type/white_papers_and_tech_docs/22007.pdf)

_an exceptionally complete coverage of Athlon-oriented

magic at both the C and x86 assembly levels_

* [Intel Architecture Optimization Reference Manual](ftp://download.intel.com/design/PentiumII/manuals/24512701.pdf)

[Intel Pentium 4 Processor Optimization Reference
Manual](http://developer.intel.com/design/pentium4/manuals/248966.htm)

_Intel's equivalents to the AMD document above.

very x86-oriented (including MMX, SSE, and SSE2)_

* [The PowerPC Compiler Writer's Guide](http://www-01.ibm.com/chips/techlib/techlib.nsf/techdocs/852569B20050FF7785256996007558C6)

* [Technical Site Index](http://www.azillionmonkeys.com/qed/asmexample.html) for azillionmonkeys 

_lots of stuff, including hacks in x86 and C_

* [Reciprocal Multiplication, a tutorial](http://www.cs.uiowa.edu/~jones/bcd/divide.html)

_a really nice piece of work by Doug Jones..._

* [Digital Signal Processing Tricks (from comp.dsp)](http://www.dspguru.com/comp.dsp/tricks/)

* [various good algorithms](http://remus.rutgers.edu/~rhoads/Code/code.html)

* [Programming Pearls](http://www.cs.bell-labs.com/cm/cs/pearls/)

book online

* [Hacker's Delight](http://www.aw.com/catalog/academic/product/1,4096,0201914654,00.html)

is a book that seems to talk about many of the same issues discussed

on this page

* [Bit Permutations](http://programming.sirrida.de/)

by Jasper Neumann, with very nice diagrams explaining them

