---
title: Heng Li's Mysterious New Program
tags: []
categories:
- blog
---
Heng Li is developing [a new code](https://github.com/lh3/bfc), but the github
page does not have any comment on what it is. I am guessing it is a Bloom
filter-based short read error-correction program, where you give an input
fastq file and the program will output the error-corrected file with erroneous
nucleotide marked in small letters.
<!--more-->

>

Usage: bfc [options]

Options:

-s FLOAT approx genome size (k/m/g allowed; change -k and -b) [unset] 

-k INT k-mer length [33] 

-t INT number of threads [1] 

-b INT set Bloom filter size to pow(2,INT) bits [33] 

-H INT use INT hash functions for Bloom filter [4] 

-d FILE dump hash table to FILE [null] 

-E skip error correction 

-r FILE restore hash table from FILE [null] 

-w INT no more than 5 ec or 2 highQ ec in INT-bp window [10] 

-c INT min k-mer coverage [3] 

-D discard uncorrectable reads 

-v show version number 

-h show command line help 

Personally I look forward to it for another reason. Both Heng Li and the
authors of kmc2 write super-efficient codes, and it seems like the fastq
readers of kmc2 team is winning over Heng Li's klib. Unfortunately, I have not
figured out the secret sauce of the Polish group and this code will help me
make a direct comparison.

