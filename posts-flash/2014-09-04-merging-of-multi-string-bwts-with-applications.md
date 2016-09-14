---
title: Merging of Multi-String BWTs with Applications
tags: []
categories:
- blog
---
[Code site](http://code.google.com/p/msbwt/wiki/CommandLineInterface)
<!--more-->

> Msbwt is a package for combining strings from sequencing into a data
structure known as the multi-string Burrows Wheeler Transform (MSBWT). This
structure allows for querying a k-mer in O(k) time regardless of how many
strings are present in the MSBWT. This particular package was created
originally for merging MSBWTs after creation. In short, this allows for
multiple datasets to be combined into a single structure which allows for
queries over both data sets simultaneously.

Included in this package are implementations of MSBWT creation algorithms as
described by Bauer et al. in "Lightweight BWT construction for very large
string collections" for different file types. Furthermore, the algorithm for
merging these MSBWTs from Holt and McMillan in "Merging of Multi-String BWTs
with Applications" is also implemented.

Currently, some rudimentary query utilities are also in place on the command
line interface. However, we recommend to anyone wishing to perform some
dynamic/interactive queries to use the API provided by the source code.

For common usage, please type after installation:

msbwt -h

Detailed Usage

msbwt cffq

Create From FastQ (cffq) will create a MSBWT from a list of supplied FastQ
files. This method uses the "column-wise" approach described by Bauer et al.
in "Lightweight BWT construction for very large string collections". The
algorithm is not computationally challenging, but requires a significant
amount of disk I/O. This command is a combination of two subcommands "pp" and
"cfpp".

-p numProcesses - the number of processes supplied to the algorithm 

-u, --uniform - indicates that all reads in the FastQ files have uniform length (faster than non-uniform) 

msbwt pp

Pre-Process will perform the first stage of the MSBWT construction algorithm.
Specifically, it extracts all reads from a list of FastQ files and stores them
in a "column-wise" manner to be processed later. It creates a series of seq
files (which can be deleted after creating the full MSBWT) that are used for
the "cfpp" function call.

-u, --uniform - indicates that all reads in the FastQ files have uniform length (faster than non-uniform) 

msbwt cfpp

Create From Pre-Process is the second stage of the MSBWT construction
algorithm. Specifically, it takes the extracted reads (in a different format
from "pp" function) and builds the MSBWT in a "column-wise" manner. The final
result is a msbwt.npy file in the supplied directory.

-p numProcesses - the number of processes supplied to the algorithm 

-u, --uniform - indicates that all reads in the FastQ files have uniform length (faster than non-uniform) 

msbwt merge

This is an implementation of the merge algorithm described by Holt and
McMillan in "Merging of Multi-String BWTs with Applications". Specifically, it
takes as input multiple MSBWT and interleaves them together such that the
final result includes all strings from the inputs. It also generates an
interleave vector used to identify the original sources of each string.
Currently, the maximum number of inputs is 256.

-p numProcesses - the number of processes supplied to the algorithm 

msbwt query

This provides command line access to the most basic of queries that can be
provided to a MSBWT. Given a MSBWT and k-mer, it will return the number of
times that k-mer occurs in the string collection.

-d, --dump-seqs - Modifies the output to also dump each string containing the k-mer and its dollar ID 

msbwt massquery

This provides command line access to the basic k-mer count for a list of
provided k-mers. It will take as input a file containing line separated k-mers
and return a list of counts. Output is returned in CSV format of k-mer,
counts.

-r, --rev-comp - Modifies the output to also return reverse complemented k-mer counts in the CSV 

msbwt compress

This will take a MSBWT and compress it using a rudimentary run-length
encoding. The compressed structure can still be search, but auxiliary
structures will have to be built (automatically) before the searches take
place.

-p numProcesses - the number of processes supplied to the algorithm 

msbwt decompress

This will take a compressed MSBWT and decompress it back to byte-per-symbol
encoding. Auxiliary structures will have to be built (automatically) before
the searches take place.

-p numProcesses - the number of processes supplied to the algorithm

[Link](http://bioinformatics.oxfordjournals.org/content/early/2014/08/28/bioin
formatics.btu584)

> Motivation: The throughput of genomic sequencing has increased to the point
that is overrunning the rate of downstream analysis. This, along with the
desire to revisit old data, has led to a situation where large quantities of
raw, and nearly impenetrable, sequence data is rapidly filling the hard drives
of modern biology labs. These datasets can be compressed via a multi-string
variant of the Burrows-Wheeler Transform (BWT), which provides the side
benefit of searches for arbitrary k-mers within the raw data, as well as, the
ability to reconstitute arbitrary reads as needed. We propose a method for
merging such datasets for both increased compression and downstream analysis.

Results: We present a novel algorithm that merges multi-string BWTs in
O(LCS*N) time where LCS is the length of their longest common substring
between any of the inputs and N is the total length of all inputs combined
(number of symbols) using O(N * log2(F)) bits where F is the number of multi-
string BWTs merged. This merged multi-string BWT is also shown to have a
higher compressibility compared to the input multi-string BWTs separately.
Additionally, we explore some uses of a merged multi-string BWT for
bioinformatics applications.

Availability: The MSBWT package is available through PyPI with source code
located at https://code.google.com/p/msbwt/.

