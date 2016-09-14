---
title: Khash by Attractive Chaos
tags: []
categories:
- blog
---
While trying to understand BWA and BWA MEM code, we came across a good blog
site by ['Attractive Chaos'](http://attractivechaos.wordpress.com/2011/09/16
/speeding-up-khash-with-a-power-of-2-bucket-count/) that the readers will find
helpful.
<!--more-->

Here is the relevant post on [khash](https://github.com/attractivechaos/klib)
\-

[Speeding up khash with a power-of-2 bucket
count](http://attractivechaos.wordpress.com/2011/09/16/speeding-up-khash-
with-a-power-of-2-bucket-count/)

but in another recent commentary, the author also spent time to provide useful
tips on how to parallelize code. Interestingly, we were scratching our head
about the same topic, when we found the following commentary.

[Parallelizing simple for
loops](http://attractivechaos.wordpress.com/2013/10/11/parallelizing-simple-
for-loops/)

> I implemented a heap-free, lock-free and wait-free scheduler for
parallelizing simple independent for loops. For example, if we have a piece of
code

`data_type *data;

for (int i = 0; i < N; ++i)

do_work(data, i);`

where each cycle is largely independent of other cycles, we can process the
loop with 4 threads:

`data_type *data;

kt_for(4, do_work, data, N);`

The 4 threads will end at about the same time even if each cycle takes very
different time to process.

The scheduler uses a simplified task stealing algorithm to balance the load of
each thread. Initially, given m threads, kt_for() assigns the i-th task/cycle
to thread i%m. If a thread finishes earlier than other threads, the thread
will steal a task from the most loaded thread. Thus as long as there remain
enough tasks, no threads will be idle.

Many other commentaries are informative. The best part - [author chooses to be
anonymous](http://attractivechaos.wordpress.com/about/) in this age of
narcissism. It must be a bioinformatics guy from Asia.

Bookmarked !

\-----------------------------

Getting back to klib and khash, what is the secret behind their performance?
The author [explains](https://github.com/attractivechaos/klib) \-

> Klib is fast partly because the compiler knows the key-value type at the
compile time and is able to optimize the code to the same level as type-
specific code. A generic library written with void* will not get such
performance boost.

Massively inserting code upon instantiation may remind us of C++'s slow
compiling speed and huge binary size when STL/boost is in use. Klib is much
better in this respect due to its small code size and component independency.
Inserting several hundreds lines of code won't make compiling obviously
slower.

The above is one reason we try to avoid STL and boost. The ease they provide
in coding is often lost in performance. We are ready to take some pain in
coding so that the code remains the best performing, instead of building the
[coolest looking Yugo](http://content.time.com/time/specials/2007/article/0,28
804,1658545_1658533_1658529,00.html).

Klib library takes all important functions to macro so that function calls
turn into macro replacements to be sorted out at the compile time.

`#define kv_push(type, v, x) do { \

if ((v).n == (v).m) { \

(v).m = (v).m? (v).m<<1 : 2; \

(v).a = (type*)realloc((v).a, sizeof(type) * (v).m); \

} \

(v).a[(v).n++] = (x); \

} while (0)

`

