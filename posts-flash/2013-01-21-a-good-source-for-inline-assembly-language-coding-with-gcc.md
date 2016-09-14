---
title: Good Sources for gcc Inline Assembly Language Coding and Multi-threading
tags: []
categories:
- blog
---
The file hashfunctions.c in SOAPdenovo2 has many hardware intensive functions,
and one of them is coded in assembly language.
<!--more-->

`

static uint32_t cpuid ( uint32_t functionInput )

{

uint32_t eax;

uint32_t ebx;

uint32_t ecx;

uint32_t edx;

#ifdef __PIC__

asm ( "pushl %%ebx\n\t" /* save %ebx */

"cpuid\n\t"

"movl %%ebx, %[ebx]\n\t" /* save what cpuid just put in %ebx */

"popl %%ebx" : "=a" ( eax ), [ebx] "=r" ( ebx ), "=c" ( ecx ), "=d" ( edx ) :
"a" ( functionInput )

: "cc" );

#else

asm ( "cpuid" : "=a" ( eax ), "=b" ( ebx ), "=c" ( ecx ), "=d" ( edx ) : "a" (
functionInput ) );

#endif

return ecx;

}

`

We were looking for a good source on assembly language features of gcc and
found [this website](http://www.ibiblio.org/gferg/ldp/GCC-Inline-Assembly-
HOWTO.html). Please note that there are two different formats - Intel code and
AT&T; code. SOAPdenovo2 seems to be following AT&T; format.

\------------------------

Separately, we were searching for few good websites on multi-threading and
found following two excellent links -

[CS360 Lecture notes -- Setjmp](http://web.eecs.utk.edu/~plank/plank/classes/c
s360/360/notes/Setjmp/lecture.html)

[How to multithread C code - a Stackoverflow
thread](http://stackoverflow.com/questions/3908031/how-to-multithread-c-code)

Enjoy !!

