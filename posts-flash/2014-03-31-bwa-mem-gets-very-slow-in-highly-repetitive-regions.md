---
title: BWA-MEM Gets Very Slow in Highly Repetitive Regions
tags: []
categories:
- blog
---
The other day, we were benchmarking BWA-MEM and noticed something odd (to our
naive eyes). We created a number of 150nt simulated reads from the Arabidopsis
genome by inserting a 3nt deletion at the middle of otherwise perfectly
matching reads. All files with about 10,000 reads aligned very quickly (5-6
seconds), but strangely one file with the same number of reads took 7 minutes
!!
<!--more-->

After repeated checking, we emailed Heng Li and he was very kind to respond
immediately. The speed of BWA-MEM changes quite a bit in the repetitive
regions of the genome.

> If you are simulating reads from the human centromeres and then map back,
these reads will take 100+ times longer time. I guess your case is similar.

That is not an unusual aspect of BWA-MEM per se as further explained by Heng.

> Every mapper is tens to thousands of times slower for highly repetitive
reads. There is no way to solve that as far as I see.

We brought this up, because Rayan Chikhi [posted a genome assembly question in
Biostar](http://www.biostars.org/p/96467/#96553) \-

> Has anyone performed assembly with Nextera mate pairs and has seen the
following problem?

We're doing mammalian assemblies using Nextera 8 kbp-insert mate-pairs, and
the results are abnormal. The total assembly size is way larger than expected:
because it has 1 Gbp of NNN's in scaffolds. The total contigs size matches the
genome size.

Some detailed information regarding the data and the assembly:

mammalian genome

Lib1: HiSeq 150 bp paired-end 500 bp insert, 30x coverage

Lib2: HiSeq 150 bp mate-pairs 3kbp insert (not sure about protocol), 10x
coverage

Lib3: HiSeq 150 bp mate-pairs 8kbp insert (Nextera), 30x coverage

assembler: SOAPdenovo2 latest

Lib1 and Lib2 were adapter-trimmed using nesoni

Lib3 was adapter-trimmed using nextclip (which had a positive impact on
scaffold N50) and to those familiar with nextclip, we kept the A-B-C
tags: []
categories only.

Some extra steps we tried:

When we assemble Lib1 and Lib2 together, the total scaffolds size is what we
expect (3 Gbp, 30 Kbp scaffold N50). So all is fine here.

When we assemble all libs together, the total scaffolds size is too high (4
Gbp, 150 Kbp scaffold N50).

When Lib3 is untrimmed, the total scaffolds size is terrible (6 Gbp) and
contigs size is also odd (3.5 Gbp).

Whether Lib3 is included in the contigs step or not (asm_flags=2 or 3) does
not have a significant impact on the results.

His problem was solved by going to another scaffolding program (SSPACE)
instead of SOAPdenovo2, but why did SOAPdenovo2 fail? Was it having hard time
resolving repeats? We bring that up, because Rayan also mentioned that BWA-MEM
took unusually long time to align the reads to the assembly and his suspected
reason was hardware issues. That is quite possible, but we like to highlight
here that BWA-MEM can run slow for other reasons as well.

