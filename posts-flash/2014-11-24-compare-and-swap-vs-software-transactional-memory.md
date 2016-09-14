---
title: "'Compare and swap' vs Software Transactional Memory"
tags: []
categories:
- blog
---
Programmers often use 'compare and swap' or other hardware provided options to
get [atomicity ](https://en.wikipedia.org/wiki/Linearizability), but another
alternative is to use software transactional memory. Please check the
folliwing link for a good introduction.
<!--more-->

[The Basics of Software Transactional
Memory](http://goodmath.scientopia.org/2012/01/22/the-basics-of-software-
transactional-memory/)

> As I see it, STM is based on two fundamental concepts:

Optimism. In software terms, by optimism, we mean that we're going to plow
ahead and assume that there aren't any errors; when we're done, we'll check if
there was a problem, and clean up if necessary. A good example of this from my
own background is source code control systems. In the older systems like RCS,
you'd lock a source file before you edited it; then you'd make your changes,
and check them in, and release the lock. That way, you know that you're never
going to have two people making changes to the same file at the same time. But
the downside is that you end up with lots of people sitting around doing
nothing, waiting to get the lock on the file they want to change. Odds are,
they weren't going to change the same part of the file as the guy who has the
lock. But in order to make sure that they can't, the locks also block a lot of
real work. Eventually, the optimistic systems came along, and what they did
was say: "go ahead and edit the file all you want. But before I let you check
in (save) the edited file to the shared repository, I'm going to make sure
that no one changed it in a way that will mess things up. If I find out that
someone did, then you're going to have to fix it."

Transactions. A transaction is a concept from (among other places) databases.
In a database, you often make a collection of changes that are, conceptually,
all part of the same update. By making them a transaction, they become one
atomic block - and either the entire collection all succeedd, or the entire
collection all fail. Transactions guarantee that you'll never end up in a
situation where half of the changes in an update got written to the database,
and the other half didn't.

A more technically oriented introduction is in the following link.

[Beyond Locks: Software Transactional
Memory](http://bartoszmilewski.com/2010/09/11/beyond-locks-software-
transactional-memory/)

And when everything else fails, you can check what various people at
stackoverflow suggest.

[Non-Toy Software Transactional Memory for C or
Java](http://stackoverflow.com/questions/15064173/non-toy-software-
transactional-memory-for-c-or-java)

**Implementation and Language support**

STM is built into Haskell and Clojure as core language feature and is
supported in [gcc 4.7 onward](https://gcc.gnu.org/wiki/TransactionalMemory).
Python programmers are recommended to [quit or join the Haskell
community](http://www.homolog.us/blogs/blog/2012/09/26/bye-bye-python-enter-
haskell/).

> The implementation of transactional memory is transparent to the program and
most of it resides in a runtime library (libitm in GCC). Transactions thus
always provide the same guarantees, even though performance at runtime might
be different depending on the implementation that is being used. In general,
implementations come in two forms: a Software Transactional Memory (STM)
system uses locks or other standard atomic instructions to do its job. A
Hardware Transactional Memory (HTM) system uses multi-word synchronization
operations of the CPU to implement the requirements of the transaction
directly (e.g., see the Rock processor). Because most HTM systems are likely
to be best effort facilities (i.e., not all transactions can be executed using
HTM), practical TM implementations that incorporate HTM also have a STM
component and are thus termed Hybrid Transactional Memory systems.

or you can look into [the following libraries](https://en.wikipedia.org/wiki/S
oftware_transactional_memory#C.2FC.2B.2B).

> TinySTM a time-based STM and Tanger to integrate STMs with C and C++ via
LLVM.

The Lightweight Transaction Library (LibLTX), a C implementation by Robert
Ennals focusing on efficiency and based on his papers "Software Transactional
Memory Should Not Be Obstruction-Free" and "Cache Sensitive Software
Transactional Memory".

LibCMT, an open-source implementation in C by Duilio Protti based on
"Composable Memory Transactions".[6] The implementation also includes a C#
binding.

TARIFA is a prototype that brings the "atomic" keyword to C/C++ by
instrumenting the assembler output of the compiler.

Intel STM Compiler Prototype Edition implements STM for C/C++ directly in a
compiler (the Intel Compiler) for Linux or Windows producing 32 or 64 bit code
for Intel or AMD processors. Implements atomic keyword as well as providing
ways to decorate (declspec) function definitions to control/authorize use in
atomic sections. A substantial implementation in a compiler with the stated
purpose to enable large scale experimentation in any size C/C++ program. Intel
has made four research releases of this special experimental version of its
product compiler.

stmmap An implementation of STM in C, based on shared memory mapping. It is
for sharing memory between threads and/or processes (not just between threads
within a process) with transactional semantics. The multi-threaded version of
its memory allocator is in C++.

CTL An implementation of STM in C, based on TL2 but with many extensions and
optimizations.

The TL2 lock-based STM from the Scalable Synchronization research group at Sun
Microsystems Laboratories, as featured in the DISC 2006 article "Transactional
Locking II".

Several implementations by Tim Harris & Keir Fraser, based on ideas from his
papers "Language Support for Lightweight Transactions", "Practical Lock
Freedom", and an upcoming unpublished work.

RSTM The University of Rochester STM written by a team of researchers led by
Michael L. Scott.

G++ 4.7 now supports STM for C/C++ directly in the compiler. The feature is
still listed as "experimental", but may still provide the necessary
functionality for testing.

Anybody with experience with the above libraries?

