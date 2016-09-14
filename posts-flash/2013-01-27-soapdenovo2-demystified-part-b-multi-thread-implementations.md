---
title: SOAPdenovo2 Demystified &ndash; part (b) [multi-thread implementations]
tags: []
categories:
- blog
---
We apologize for not being able to post our remaining SOAPdenovo2-related
commentaries. So far, we presented a [general overview of
SOAPdenovo2](http://www.homolog.us/blogs/2013/01/05/soapdenovo2-demystified-
part-1/), and also [looked at library functions and their associated
algorithms](http://www.homolog.us/blogs/2013/01/05/soapdenovo2-demystified-
part-a/). Today, we will go through files, whose names start with prl
(prlHashCtg.c, prlHashReads.c, prlRead2Ctg.c, prlRead2path.c,
prlReadFillGap.c) and check their threading-related functions. Two additional
files - cutTipPreGraph.c and read2edge.c - also implemented multi-threading
codes and will be covered in this discussion.
<!--more-->

[Multi-threading](http://en.wikipedia.org/Multithreading_%28software%29#Multit
hreading) is a method of allowing multiple cores in the processor to be used
to perform parallel execution of codes. Implementing multi-threaded code needs
two steps -

(i) to modify codes so that threading-related lines are implemented. That is
the easy step,

(ii) to figure out or change the algorithm so that all threads are independent
and do not result in any race conditions. That is the hard step.

\-------------------------------

(i)

Let us discuss the easy part first. All mentioned files have the following
functions -

1\. `static void threadRoutine ( void * para )`

2\. `static void creatThrds ( pthread_t * threads, PARAMETER * paras )`

3\. `static void thread_wait ( pthread_t * threads ) `

4\. `static void sendWorkSignal ( unsigned char SIG, unsigned char *
thrdSignals )`

Together, they manage the parallelization. The whole process is not at all
complicated, and you will have to work through one example step by step and
then simply use some template code and fill up the blocks.

If you are not at all familiar with multi-threading,
[here](http://www.codeproject.com/Articles/212377/Multithreading-Demystified)
is a good introduction to the terms. Here, instead of describing sample codes,
we will go inside SOAPdenovo2 files and explain how they parallelize by
working through an example.

We will look into prlRead2Ctg.c file. For the time being, let us forget about
what it does, although you can guess that from the file-name. The file has
functions to map the reads to the contigs.

The function createThrds usually has the following generic syntax.

`

static void creatThrds ( pthread_t * threads, PARAMETER * paras )

{

unsigned char i;

int temp;

for ( i = 0; i < thrd_num; i++ )

{

if ( ( temp = pthread_create ( &threads;[i], NULL, ( void * ) threadRoutine, &
( paras[i] ) ) ) != 0 )

{

fprintf ( stderr, "Create threads failed.\n" );

exit ( 1 );

}

}

fprintf ( stderr, "%d thread(s) initialized.\n", thrd_num );

}`

The function creates number of threads, and calls **threadRoutine **for each
one.

The function **sendWorkSignal **also usually has very generic syntax.

`

static void sendWorkSignal ( unsigned char SIG, unsigned char * thrdSignals )

{

int t;

for ( t = 0; t < thrd_num; t++ )

{

thrdSignals[t + 1] = SIG;

}

while ( 1 )

{

usleep ( 10 );

for ( t = 0; t < thrd_num; t++ )

if ( thrdSignals[t + 1] )

{

break;

}

if ( t == thrd_num )

{

break;

}

}

}

`

Real heavy lifting gets done by the function **threadRoutine**. It calls
functions for execution of individual threads.

In the bigger scheme, the main function of the file **prlRead2Ctg** calls both
creatThrds and sendWorkSignal, and then creatThrds calls all little functions.
It is that simple !!

![write-blog](http://www.homolog.us/blogs/wp-content/uploads/2013/01/write-
blog1-150x150.png)

\---------------------------------

(ii) If the above part appears simple, you are wrong. The real hard part is in
understanding the algorithm and splitting the code into independent threadable
units.

Think about a computer algorithm+code as a bowl of noodles like this one.

![images](http://www.homolog.us/blogs/wp-content/uploads/2013/01/images-
150x150.jpg)

When you multi-thread, each thread needs to look like this -

![images2](http://www.homolog.us/blogs/wp-
content/uploads/2013/01/images2-150x150.jpg)

Untangling the pieces of noodles is the main challenge. The task is less
complex, when we map thousands of reads on the contigs. Mapping of each read
is an independent problem, whose result is unaffected by mapping of another
read. That is why most multi-threaded files in SOAPdenovo2 are mapping-
related.

We will add more about following seven files, and [update their wiki
pages](http://homolog.us/wiki1/index.php?title=SOAPdenovo2) in the coming
days.

NameMain functionSingle functionsPurpose

prlHashCtg.c

prlContig2nodes

singleKmer, chopKmer4read

Chops contigs into k-mers

prlHashReads.c

prlRead2HashTable

singleKmer, chopKmer4read, thread_mark, thread_delow

prlRead2Ctg.c

prlRead2Ctg

parse1read, searchKmer, chopKmer4read

prlRead2path.c

prlRead2edge

searchKmer, chopKmer4read, parse1read, search1kmerPlus, thread_add1preArc,

prlReadFillGap.c

prlReadsCloseGap

emptyDarray, check1scaf

cutTipPreGraph.c

Mark1in1outNode

thread_mark

read2edge.c

Read2edge, Read2edge2

chopKmer4read, searchKmer1read

