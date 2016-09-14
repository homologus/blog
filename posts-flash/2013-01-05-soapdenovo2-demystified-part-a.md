---
title: SOAPdenovo2 Demystified - part (a)
tags: []
categories:
- blog
---
**Library Functions**
<!--more-->

The 'library files' contain set of functions being reused in many parts of the
program. They should be reusable even outside SOAPdenovo2. If you are writing
a new bioinformatics program, you can borrow them or otherwise have to write
similar functions on your own.

Here are the general description of various library files and functions. We
are working through their wiki pages, and will update this commentary, if we
find something new.

i) **darray.c, stack.c**

These two files have functions to create [dynamic
arrays](http://en.wikipedia.org/wiki/Dynamic_array) and
[stacks](http://en.wikipedia.org/wiki/Stack_%28abstract_data_type%29). Most
computer scientists know the purpose of those data structures.

[darray.c](http://homolog.us/wiki1/index.php?title=SOAPdenovo2:darray.c): It
has functions _createDarray_ to create dynamic array of given size,
_darrayPut_ dynamically allocates space to add element at given index,
_darrayGet_ to get an element from given index, _emptyDarray _ to empty the
dynamic array and _freeDarray_ to free the dynamically allocated space.
Structure of the array is defined in darray.h.

`typedef struct dynamic_array

{

void * array;

long long array_size;

size_t item_size;

long long item_c;

} DARRAY;`

[stack.c](http://homolog.us/wiki1/index.php?title=SOAPdenovo2:stack.c):
Dynamically allocated stack with functions createStack, emptyStack, freeStack,
stackBackup, stackPop, stackPush.

ii) **fib.c, dfib.c, fibHeap.c, dfibHeap.c**

[Fibonacci](http://en.wikipedia.org/wiki/Leonardo_of_Pisa) was an Italian
mathematician of 11th century, whose name was not Fibonacci and is famous for
a number series that he did not discover !! Isn't that cool? Here is the more
interesting part. The implications of Fibonacci numbers are under-appreciated,
because they are not part of mathematical underpinning of our physical
sciences. For example, stock market data often show repetitions of Fibonacci
distribution and fractal patterns, but standard economics texts never analyze
such patterns.

Distraction aside, in computer science, [Fibonacci
heaps](http://en.wikipedia.org/wiki/Fibonacci_heap) are expected to have
faster access time than binary heaps.

[fib.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:fib.c): Well-
written set of Fibonacci heap functions from John-Mark Gurney. They are
distributed under MIT-type license. Do not forget to also grab fib.h, dfib.h
and dfibpriv.h.

[dfib.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:dfib.c): Another
of Gurney's creations.

[fibHeap.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:fibHeap.c):
BGI's wrapper on Gurney's functions in fib.c.

[dfibHeap.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:dfibHeap.c):
BGI's wrapper on Gurney's functions in dfib.c.

iii) **lib.c, check.c, mem_manager.c**

[lib.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:lib.c): Functions
in this file are used to check the read libraries.

[check.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:check.c):
Functions here are used to check whether files exist before opening them, or
there is enough memory before allocating more space.

[mem_manager.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:mem_manager
.c): Some kind of memory manager to dynamically allocate space for hashes,
heaps, etc.

iv) **kmer.c, kmerhash.c, newhash.c, hashFunctions.c**

Following files should be self-explanatory for anyone working on de Bruijn
graph-based algorithms.

[kmer.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:kmer.c): Processes
kmers. The important part here is that BGI's library can handle kmers of
length up to 127 nucleotides (2^7-1). It is done by splitting higher and lower
halves of a kmers into two separate spaces.

[kmerhash.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:kmerhash.c):
Various kmer-related operations.

[newhash.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:newhash.c):
Replacement of kmerhash.c mentioned above.

[hashFunctions.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:hashFunct
ions.c): Describes the hash function. This file must be the center of universe
:), because it has some embedded assembly language code. What is crc table?
[Cyclic redundancy check](http://en.wikipedia.org/wiki/Computation_of_CRC) or
something else?

v) **seq.c, readseq1by1.c**

[seq.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:seq.c): This file
has functions to write A/T/G/C sequences into tightstring format.

[readseq1by1.c](http://homolog.us/wiki/index.php?title=SOAPdenovo2:readseq1by1
.c): Reads sequence 'one by one' - the purpose of this file should be very
clear from its name. It has functions to read input files of different forms -
fastaq, bam, sam, gzip, etc.

