---
title: Data Compression Algorithms
tags:
- compression
- search
- bowtie
- BWT
- BWA
categories:
- blog
---
All of us are familiar with zip/unzip or gzip/gunzip programs for compressing
and uncompressing large genomic files. How do various program compress and
decompress large files? Today we shall broadly review data compression schemes
and explain how Burrows Wheeler transform can help in compressing data. This
topic may seem unrelated to search programs, but it is indeed one of the
necessary technical blocks in understanding FM-index.
<!--more-->

We earlier discussed about transforms and reversible transforms. Please note
that all compression schemes are reversible transforms on input files. They
are transforms, because they turn the input into something else. They have to
be reversible, or otherwise you cannot recover your input file from its
compressed form.

Intuitively you can see that some files beg to be compressed. For example, if
a sequence has very long chain of 10000 As, you can save space by writing
'10000A' instead of keeping a long chain of 'AAAAAAAAAAAA....'. The
compression algorithm will go through the genome file, look for long
repetitive chains and replace them with a number followed by a letter. The
decompression algorithm will go through a compressed file and replace each
instance of number followed by letter with long chain of letters. Neat? A more
sophisticated program may even replace 'TATATATATATATATA' by '8TA' and so on.

Unfortunately, such easy cases are rare. Most genomic files provide very few
opportunities for compressing long chains of simple repetitive sequences.
However, you can transform the genome file into something else with long
repetitive sequences and then use the above compression scheme. How can you do
that? As we explained earlier in '[Finding us in
homolog.us](http://www.homolog.us/blogs/2011/10/03/finding-us-in-homolog-
us/)', Burrows Wheeler transform changes a text in such a way that identical
characters tend to come together. So, you can design a compression scheme that
first performs BWT on the genome sequence and then replaces long chain of
letters by numbers+letters. The reverse compression executes the opposites of
above steps in reverse order. The above method will give back the original
genome sequence from its compressed form, because BWT is reversible.

Popular programs like zip or gzip do not use BWT. To learn how they save
space, you need to understand how computers store data.

A computer does not read English characters, or Chinese characters for that
matter. It only knows two numbers - '0' and '1'. To store English text in a
computer, all English characters has to be assigned some number with
combination of 0s and 1s. For example, English character 'A' can be given a
number '001000001', 'B' can be given a number '001000010' and so on. This is
called binary representation. Why do we need so many 0s and 1s to represent
one character? Because we need to have enough room for 26 small letter, 26
capital letters, numbers 0-9, brackets, asterix, semi-colon and everything
else you see on the keyboard. **All those characters are assigned binary form
of fixed width.**

That is quite a luxury, if all you have are As, Cs, Gs and Ts. You can pick
binary forms of all As as '00', all Cs as '01', all Ts as '10' and Gs as '11'
and save quite a bit of space. Popular file compression programs do exactly
that. They find out which characters are present in the file, and create a new
binary representation removing all the clutter.

In fact they go one step further, and adjust lengths of binary representations
of various characters according to their frequencies in the text. For example,
if you have a GC-rich genome, you may assign 'G' and 'C' with smaller binary
representations than 'A' and 'T', and save even more space. The letter 'e' has
much higher abundance than the letter 'z' in regular English text. So,
assigning 'e' with smaller binary representation than 'z' results in
significant space reduction. All these are taken care of by the popular
compression algorithms. Various coding schemes such as [Huffman
coding](http://en.wikipedia.org/wiki/Huffman_coding), [arithmetic
coding](http://en.wikipedia.org/wiki/Arithmetic_coding), etc. are used to
perform this task.

An understanding of how compression works can sometimes help you get better
compression by reformatting the data. We had a huge file of K-mers that we
wanted to move from one machine to another. When we applied gzip to the
original file, the 13G file reduced in size to 3G. So, we decided to sort the
file and then apply gzip. The sorting step brought down the size of the
compressed file to only 250 Mb. Sorting is an expensive step, but it resulted
in 52 fold reduction in size instead of 4 fold reduction for the unsorted
file. Sorting brought identical words together and helped the compressing
program to replace them by number+word, as we explained earlier.

