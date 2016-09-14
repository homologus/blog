---
title: Excellent Software Engineering in KMC
tags: []
categories:
- blog
---
I did not have much respect for ['Boosted'](http://www.boost.org/) C++
programmers in bioinformatics until I went through KMC code. KMC, or rather
its latest version KMC2, is currently the fastest (and leanest) kmer counting
program. A kmer counting program is conceptually very naive, and that means
the faster programs are reflections of programmers' knowledge about various
hardware and data structure concepts. For example, Jellyfish uses [compare-
and-swap](http://en.wikipedia.org/wiki/Compare-and-swap) feature of modern
processors to make hash table updates near concurrent. BFcounter and a number
of other programs use [Bloom
filter](http://www.homolog.us/blogs/blog/2012/03/29/using-bloom-filter-a
-simple-introduction-for-bioinformaticians/), a data structure concept
unrelated to bioinformatics.
<!--more-->

KMC, the earlier program, was disk-based and memory-light just like [Chikhi et
al.'s DSK](http://www.homolog.us/blogs/blog/2013/02/06/dsk-k-mer-counting-
with-very-low-memory-usage/). However, KMC showed significant speed
improvement over DSK by using extensive parallelization in various steps. KMC2
has further improvement over KMC [due to its use of minimizer
concept](http://www.homolog.us/blogs/blog/2014/07/11/minimizer-revolution-
continues-with-kmc-2-k-mer-counter/). In fact, KMC2 is also an improvement
over MSPcounter, another minimizer-based kmer counting program, because it
modifies minimizers to 'signatures' to avoid too many subreads going to the
same bucket.

Those algorithmic contributions aside, KMC2 code is a pleasure to read. The
code is organized into four subdirectories (kmer_counter, kmc_dump,
kmc_dump_sample, kmc_api), among which 'kmer_counter' is most important. The
following figure from the kmc2 paper displays the flow diagram of the code.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2014/12/Capture1-259x300.png)

KMC code is multithreaded and uses a number of queues to handle
parallelization. What I found quite amazing is that it completed kmer counting
in about the same time another test code written by me barely went through a
giant FASTQ file. That means the biggest bottleneck of KMC2 is in reading
fastq file from the disk and not in actual processing and counting of kmers. I
am working through various classes within the code, and as I proceed, the
following blocks will be updated. If you have any further insight, please feel
free to let me know in the comment section below.

**kmer_counter.cpp:** The main code is in kmer_counter.cpp. It defines the class 'CApplication' that calls various classes through CKMC class. 

**kmc.h** \- defines the CKMC class that parallelizes the code and calls the classes in the files below. 

CKMC class is where all action takes place. So, let me describe it in a bit
more detail.

i) The public function SetParams(CKMCParams &_Params) sets all parameters.

ii) The public function Process() does all work by synchronizing all threads,
etc. This is the most important function in the entire program.

iii) Here is a complete list of all other private and public functions. The
names are quite descriptive of what they do.

`template  class CKMC {

bool initialized;

CStopWatch w0, heuristic_time , w1, w2;

// Parameters (input and internal)

CKMCParams Params;

// Memory monitor and queues

CKMCQueues Queues;

// Thread groups

vector gr0_1, gr0_2;

vector gr1_1, gr1_2, gr1_3, gr1_4, gr1_5; // thread groups for 1st stage

vector gr2_1, gr2_2, gr2_3; // thread groups for 2nd stage

uint64 n_unique, n_cutoff_min, n_cutoff_max, n_total, n_reads, tmp_size,
n_total_super_kmers;

// Threads

vector w_stats_fastqs;

vector*> w_stats_splitters;

vector w_fastqs;

vector*> w_splitters;

CWKmerBinStorer *w_storer;

CWKmerBinReader* w_reader;

vector*> w_sorters;

CWKmerBinCompleter *w_completer;

void SetThreads1Stage();

void SetThreads2Stage(vector& sorted_sizes);

bool AdjustMemoryLimits();

void AdjustMemoryLimitsStage2();

void ShowSettingsStage1();

void ShowSettingsStage2();

public:

CKMC();

~CKMC();

void SetParams(CKMCParams &_Params);

bool Process();

void GetStats(double &time1;, double &time2;, uint64 &_n_unique, uint64
&_n_cutoff_min, uint64 &_n_cutoff_max, uint64 &_n_total, uint64 &_n_reads,
uint64 &_tmp_size, uint64& _n_total_super_kmers);`

**kmer.h** \- defines classes Ckmer and CKmerQuake for handling Kmers without and with quality scores. 

**fastq_reader.h** \- FASTQ reader classes CFastqReader and CWStatsFastqReader. The second class is a wrapper for the first one created to perform multi-threading. 

**splitter.h** \- defines the class CSplitter that splits reads into variuous bins. This is where minimizers are computed. 

**kb_storer.h** \- defines the class CKmerBinStorer that stores bins of kmers. 

**kb_sorter.h** \- defined the class CKmerBinSorter which sorts kmers within bins. 

**kb_reader.h** \- defines the class CKmerBinReader, which reads bins from distribution phase. 

**kb_completer.h** \- defines the class CKmerBinCompleter, which complete the sorted bins and store in a file. 

**kb_collecter.h** \- defines the class CKmerBinCollector, which collects kmers belonging to a single bin.

