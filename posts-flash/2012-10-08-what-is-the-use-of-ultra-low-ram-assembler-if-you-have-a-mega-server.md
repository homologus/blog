---
title: Are Ultra-low RAM Assemblers Useful for those with Kick-ass Servers?
tags: []
categories:
- blog
---
Computer scientists have been spending great deal of time to find memory-
efficient methods for NGS assembly, as we explained in [an earlier
commentary](http://www.homolog.us/blogs/2012/10/08/succinct-de-bruijn-graphs-
from-tetsuo-shibuyas-group/). Their primary motivation is to be able to
compete with genome centers and few dedicated genome assembly groups, who
already have high-RAM servers. However, can the groups with high-RAM servers
find any use of memory-efficient assemblers?
<!--more-->

Assembling even larger sets like metagenomes is one possible answer, but even
those not working on metagenomes can use memory efficient assembler by running
assembly with many different parameters in parallel. Assembling with many
different k-mer sizes and choosing optimum k-mer is one option. With memory-
efficient assemblers, all those assemblies with multiple k-mers can be run in
parallel.

Over the weekend, we tried checking the above possibility with Minia and hit
several glitches. None of them is insurmountable, but we thought it would be
worth listing them to save others some time. Those using other assemblers need
to check with respective options, but we believe all of them will face similar
problems in one form or another.

**1\. Too many open files** Minia uses the disk extensively and opens many files (over 1000) in parallel. Unix file systems usually limit the number of files one shell can open, and you can check the limit on your machine by typing 'ulimit -n'. To increase the limit, you may have to contact your system administrator. 

2\. **Max k-mer size limited to 32** Maximum k-mer size in our code was
limited to 32. We tweaked the makefile to increase it to 64.

3\. **Disk space** Unlike 1 and 2, this is a serious problem. Minia and many
other assemblers use the disk to count k-mers in the NGS libraries. For one
human library, you may do ok with 1 Terabyte of hard-disk. If you want to run
16 similar assemblies (all odd ks between 25-57) in parallel, be ready to
start with a large disk with 16 Terabytes of empty space.

Then again, someone with 512 GB RAM servers speaks in terms of petabytes of
disk space, right? :)

\--------------

Edit.

Here is the **final answer** from C. Titus Brown -

![](http://www.homolog.us/blogs/wp-
content/uploads/2012/10/Capture6-300x120.png)

