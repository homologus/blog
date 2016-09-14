---
title: What They Never Teach You in Programming Classes
tags: []
categories:
- blog
---
While searching for efficient codes, we came across a [very useful
webpage](http://graphics.stanford.edu/~seander/bithacks.html) with many short
code snippets. What is so special about them? Let us explain by going back to
the [bit reversal example](http://www.homolog.us/blogs/2012/10/30/best-
algorithm-for-bit-reversal/) we [posted the other
day](http://www.homolog.us/blogs/2012/10/30/best-algorithm-for-bit-reversal/).
<!--more-->

You can take many programming classes (C++, Java, PERL, PHP) without finding
out that computer programming is an abstraction to hide a scary monster from
you, and that monster is called - drum beats - the computer. Nobody wants to
find out what myriads of tentacle-like wires inside a computer do, and
programming languages are easy ways to forget about that world of wires.
However, if you want to extract efficiency out of your code, it may help to
have some understanding of hardware.

We will draw a very simple model to explain how a computer works. The 'center
of universe' is a tiny unit called ALU (Arithmetic and Logical Unit - shown in
black), where all computing takes place. Data need to be dragged into ALU for
a computation to take place. The ALU is surrounded by registers for storing
data. Those registers, ALU and their control circuits together form the
microprocessor or CPU.

![](http://www.homolog.us/blogs/wp-content/uploads/2012/10/write-
blog7-300x200.png)

Once you understand that ALU is the only place, where computing takes place,
everything else about architectures of modern computers will make sense. Let
us say, you want to add 2 numbers - 5 and 7. The numbers are stored in your
hard disk, which is far, far away from ALU.

If you want to add those two numbers only once, it may make sense to carry
them to ALU, add them, and send the result 12 back to hard drive. What if you
want to add 3 to the sum of 5 and 7. Now, you need to carry 12 from hard drive
all the way back to ALU, add 3 and send back the results to hard drive. That
is not efficient at all, and computer designer introduced main memory (RAM)
for intermediate storage.

The RAM is lot closer to ALU, and you can cut down the time required for
moving numbers back and forth. Instead, you can copy numbers from hard drive
to RAM, do all computations, and then send back the final results to hard
drive after all calculations are completed.

Two problems -

(i) RAM is expensive and it is not possible to get as much space as you have
in your hard drive. RAM needs to be used efficiently.

(ii) RAM is still not close enough to the ALU, and data transportation time is
substantial.

The first problem is solved with better computing algorithms and data
structures, whereas the second problem is solved by adding another layer of
storage even closer to the ALU. This new type of storage called cache (not
shown in figure) sits right inside the CPU, but is not as close to the ALU as
the registers. Cache is more expensive that RAM, and only a little amount of
it (few MB) can be added to each CPU.

The registers are the closest to ALU, but the amount of space within them is
tiny (few bytes).

One can make his code efficient by trying to visualize this entire process of
movement of data between hard disk, main memory, caches, registers and back to
disk.

\--------------------

The second thing one does not learn in programming classes is that a computer
speaks only one language [that reads like
this](http://stackoverflow.com/questions/746171/best-algorithm-for-bit-
reversal-from-msb-lsb-to-lsb-msb-in-c).

`

.L3:

movl (%r12,%rsi), %ecx

movzbl %cl, %eax

movzbl BitReverseTable256(%rax), %edx

movl %ecx, %eax

shrl $24, %eax

mov %eax, %eax

movzbl BitReverseTable256(%rax), %eax

sall $24, %edx

orl %eax, %edx

movzbl %ch, %eax

shrl $16, %ecx

movzbl BitReverseTable256(%rax), %eax

movzbl %cl, %ecx

sall $16, %eax

orl %eax, %edx

movzbl BitReverseTable256(%rcx), %eax

sall $8, %eax

orl %eax, %edx

movl %edx, (%r13,%rsi)

addq $4, %rsi

cmpq $400000000, %rsi

jne .L3

`

Every other code, from C++ to python, gets converted to the above form
(assembly language) before ALU gets a chance to run your code.

What are the above lines saying? They are talking about moving numbers between
main memory and registers in CPU, and performing various arithmetic/logical
operations on the numbers in various registers.

Few points -

(a) The number of 'opcodes' (such as movl, movzbl, mov, compq, addq, etc.)
known by an ALU is very small. All fancy codes we write in higher level
languages finally get reduced to that tiny set.

(b) If code 1 appears elegant in high level language, but is inefficient in
assembly language, it is inefficient. No ifs and buts.

\-----------------------------------

With the above introduction, let us revisit the [solution proposed for bit
reversal](http://stackoverflow.com/questions/746171/best-algorithm-for-bit-
reversal-from-msb-lsb-to-lsb-msb-in-c).

**Point 1.** You can see how much thought was given in the first response to accommodate flow of data between memory, cache and registers. The relative efficiencies of two proposed solutions (bit twiddling and memory lookup) will vary depending on the how much cache is added in the processor. Older processors with no cache will keep the lookup table in RAM. 

**Point 2.** The bit twiddling solutions are elegant, because they try to solve problems by using the ALUs and registers as much as possible. At that level, whether a processor does branching efficiently will have much say on whether a program runs efficiently. We rarely think about those differences in our programming and hope that the compilers will take care of processor-related differences. 

**Point 3.** If Intel ever adds another opcode called 'bit reverse' or 'bre' to its set of codes for ALU, all discussions for bit reversal would be redundant. Only one line of program will be needed. 

`bre %rsi`

That is how efficient a hardware-based solution can be, but, unfortunately,
all problems cannot be solved by hardware.

