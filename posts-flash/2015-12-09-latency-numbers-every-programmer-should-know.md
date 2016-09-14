---
title: Latency Numbers Every Programmer Should Know
tags: []
categories:
- blog
---
Programming FPGA makes you start to respect latency, but the concept is useful
even in traditional CPU architecture. For example, Gene Myers made his
DALIGNER code efficient by coming up with an algorithm that can only be
understood with a deep understanding of cache hits and latency.
<!--more-->

>

L1 cache reference ......................... 0.5 ns

Branch mispredict ............................ 5 ns

L2 cache reference ........................... 7 ns

Mutex lock/unlock ........................... 25 ns

Main memory reference ...................... 100 ns

Compress 1K bytes with Zippy ............. 3,000 ns = 3 s

Send 2K bytes over 1 Gbps network ....... 20,000 ns = 20 s

SSD random read ........................ 150,000 ns = 150 s

Read 1 MB sequentially from memory ..... 250,000 ns = 250 s

Round trip within same datacenter ...... 500,000 ns = 0.5 ms

Read 1 MB sequentially from SSD* ..... 1,000,000 ns = 1 ms

Disk seek ........................... 10,000,000 ns = 10 ms

Read 1 MB sequentially from disk .... 20,000,000 ns = 20 ms

Send packet CA->Netherlands->CA .... 150,000,000 ns = 150 ms

See more [here](https://gist.github.com/hellerbarde/2843375).

