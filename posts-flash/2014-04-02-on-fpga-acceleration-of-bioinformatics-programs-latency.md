---
title: On FPGA Acceleration of Bioinformatics Programs - Latency
tags: []
categories:
- blog
---
The concept of latency is very familiar to hardware designers, but rarely to
software programmers. In fact, the entire purpose of microprocessor design
these days is to hide 'latency' from the programmers using cache and hash
functions.
<!--more-->

What is latency? It is an unavoidable component of any natural system.
Suppose, you communicate to other organizations by writing letters and those
letters take one day to write, one day to get processed by the person on the
other side, but eight days in to-and-fro mail time. How many letters will you
be able to send in a month (30 days)?

Ans - three, if the letters were all dependent on each other. You need to
receive the answer of the first letter to write the second and then wait for
another ~10 days to write the third.

What if the letters were mostly independent? In that case, you could
potentially write 30 letters a month, which is 10x speedup compared to
previous scenario. You write one letter today, write another independent one
tomorrow and so on and then go back to the first one on 10th day after
receiving its reply.

The above kind of delay is common to any system, be it writing letters or
sending data from microprocessor to storage. However, one difficulty of
accelerating 'standard' software programs is that their programmers never
incorporate 'latency' in their designs. For software programmers, latency
manifests into cache miss, but that component is not incorporated in the
design. Often the solution appears to be buying a 'faster' microprocessor,
i.e. one with more cache or make other efforts to fit data into cache.

For hardware designers, the solution is to untangle the 'for' and 'while'
loops within critical block. That is quite a bit of work given how those
programs are written.

More later...

