---
title: NGS Assembly Programs - What Hash Functions Do They Use?
tags: []
categories:
- blog
---
Few days back, a reader asked us in Twitter, whether de Bruijn graph-based
assemblers could save and reload de Bruijn graphs from one another. Short
Twitter answer was no. Long answer follows here.
<!--more-->

The graph traversal part of de Bruijn graph assembler programs is not very
complicated, and [some people do it during their vacations sipping pina colada
on a beach](http://www.homolog.us/blogs/2013/04/08/step-by-step-guide-on-
genome-assembly-with-blasr-and-python/). In [our tutorials on de Bruijn
graphs](http://homolog.us/Tutorials/index.php?p=1.1&s=1), we explained the
assembly algorithm in abstract terms but did not discuss say much about the
implementation. The real challenge faced by most assembly programs is in
dealing with large volume of data. Because the linear space covered by kmers
is very large (4^k for k-mers), all de Bruijn graph-based genome assembly
program hash kmers as their first step.

Hashing is irreversible. Therefore, if the programs want to store and retrieve
de Bruijn graphs, they will have to save the hashed matrices. The problem with
exchanging data between programs is that each program uses a different hash
function. A program should be able to save and load its own de Bruijn graph,
but no program does that because storing large number of hashed values takes
space and serves no debugging purpose.

Which hash functions are used by various assembly programs?

**Velvet**

The function is in velvet_1.2.08/src/splayTable.c.

>

static KmerKey hash_kmer(Kmer * kmer)

{

#if KMER_LONGLONGS

KmerKey key = kmer->longlongs[0];

#if KMER_LONGLONGS > 1

key ^= kmer->longlongs[1];

#endif

#if KMER_LONGLONGS > 2

key ^= kmer->longlongs[2];

#endif

key = (~key) + (key << 21);

key = key ^ (key >> 24);

key = (key + (key << 3)) + (key << 8);

key = key ^ (key >> 14);

key = (key + (key << 2)) + (key << 4);

key = key ^ (key >> 28);

key = key + (key << 31);

return key % HASH_BUCKETS_NB;

#elif KMER_LONGS

KmerKey key = kmer->longs;

key += ~(key << 15);

key ^= (key >> 10);

key += (key << 3);

key ^= (key >> 6);

key += ~(key << 11);

key ^= (key >> 16);

return key % HASH_BUCKETS_NB;

#elif KMER_INTS

return kmer->ints % HASH_BUCKETS_NB;

#elif KMER_CHARS

return kmer->chars % HASH_BUCKETS_NB;

#endif

}

It is used by doFindOrInsertOccurenceInSplayTree function in the same file.

> ABySS

ABySS uses CityHash64, which is google's latest and greatest hash function.

> * Use CityHash64 rather than Bob Jenkins' hashlittle.

The code is available in these two files - abyss-1.3.4/Common/city.cc and
abyss-1.3.4/Common/city.h, and gets pulled into HashFunction.h. You can easily
change the hash function by changing code in the following inline function.

`

#ifndef HASHFUNCTION_H

#define HASHFUNCTION_H 1

#include "city.h"

#include

#include

static inline uint64_t hashmem(const void *p, size_t n)

{

return CityHash64(static_cast(p), n);

}

#endif

`

The hash function is called by Kmer.cpp and ConstString.h.

**SOAPdenovo2**

SOAPdenovo2 uses CRC32C and you can find the code in hashFunction.c.

**AllPaths**

The code is available in allpathslg-44601/src/kmers/Kmer.h. Looks like
AllPaths uses FNV algorithm.

`

unsigned long hash() const

{ unsigned long result = 14695981039346656037ul;

unsigned char const* itr =

reinterpret_cast(mVal);

unsigned char const* end(itr+sizeof(mVal));

for ( ; itr != end; ++itr )

result = 1099511628211ul*(result ^ *itr); // FNV-1a algorithm

return result; }

`

**Minia**

Minia is a different breed of assembler, because it uses a Bloom filter or
array of hash functions. The hashing code is in minia-1.3842/Hash16.cpp. Rayan
told us that he plans to replace it with a different function.

`

inline unsigned int Hash16::hashcode( uint64_t elem )

{

uint64_t code = elem;

code = code ^ (code >> 14); //supp

code = (~code) + (code << 18);

code = code ^ (code >> 31);

code = code * 21;

code = code ^ (code >> 11);

code = code + (code << 6);

code = code ^ (code >> 22);

return (((unsigned int) code ) & mask) ;

}

`

**Ray**

Looks like Ray also uses Bloom filters. It took us some time to locate the
hash functions, because Sebastien carefully hid it away from the assembler
codes. The hash functions are available in Ray-v2.1.0/RayPlatform/cryptography
with relevant link for the original reference.

`

/*

* Basically, we take a 64-bit unsigned integer (the sign does not matter..) 

* and we compute the image corresponding to a uniform distribution. 

* 

* see http://www.concentric.net/~Ttwang/tech/inthash.htm 64 bit Mix Functions 

*/ 

uint64_t uniform_hashing_function_1_64_64(uint64_t key){

// some magic here and there.

key = (~key) + (key << 21);

key = key ^ (key >> 24);

key = (key + (key << 3)) + (key << 8);

key = key ^ (key >> 14);

key = (key + (key << 2)) + (key << 4);

key = key ^ (key >> 28);

key = key + (key << 31);

return key;

}

/*

* based on uniform_hashing_function_1_64_64, but with different values 

*/ 

uint64_t uniform_hashing_function_2_64_64(uint64_t key){

key = (~key) + (key << 31);

key = key ^ (key >> 14);

key = (key + (key << 7)) + (key << 11);

key = key ^ (key >> 13);

key = (key + (key << 4)) + (key << 8);

key = key ^ (key >> 44);

key = key + (key << 6);

return key;

}

`

**Meraculous**

Meraculous uses 'perfect hash', where multiple hash functions are selected to
avoid collision. The method is not as perfect as Minia's Bloom filter
approach. They used Bob Jenkins as base hash function and then modified the
hash function in the following manner.

`

// we wrap the hash function with the modulo of the mainHashBufferSize

// for ease of use, since so far we've always wanted the wrapped value, not

// the raw hash value

long int KeylessHash::hash( const char *str, long int mainHashBufferSize_, int
variantId )

{

/*

unsigned long hash = variantId;

int c;

while (c = *str++)

hash = ((hash << 5) + hash) + c; // hash * 33 + c

return hash % mainHashBufferSize_;

*/ 

// TO CALL Bob Jenkins:

long int seedValue = variantId; // be lazy

return ( hashFunc( ( u1 * )str, strlen( str ), seedValue ) %
mainHashBufferSize_ );

}

long int hash( const char *key, long int tableSize )

{

long int h=0;

while(*key) h=*key++ + (h<<6) + (h<<16) - h;

return h % tableSize;

}`

**spades**

Spades uses Murmurhash3 and the code is available in
spades-2.3.0/src/include/mph_index/MurmurHash3.h. We found another hash
function in spades-2.3.0/src/include/sequence/seq.hpp, but do not know what it
does. The authors of spades told us that they were moving to perfect hash.

`

PrimeNum=239;

static size_t GetHash(const DataType *data, size_t sz = DataSize) {

size_t hash = PrimeNum;

for (size_t i = 0; i < sz; i++) {

hash = ((hash << 5) - hash) + data[i];

}

return hash;

}

`

**Trinity**

This is where we gave up. Sorry folks !

**SGA - String Graph Assembler**

Jared Simpson's string graph assembler (SGA) falls into different category
from the above programs for two reasons.

(i) It uses an algorithm different from de Bruijn graphs.

(ii) No matter how hard we tried, we could never manage to compile the code.
Jared Simpson, the author of the paper, kindly offered us help to go over that
inconvenience.

However, going through the code, it appears like his program does not use
standard hashing technique of other de Bruijn assemblers. That makes sense,
because SGA pre-compresses the strings with Burrow-Wheeler transform and FM
index. Therefore, it does not have the same memory constraint as the de Bruijn
graph-based assemblers.

Edit. Jared Simpson corrected us with the following information -

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/05/Capture7-300x52.png)

[Here](https://github.com/jts/sga/blob/master/src/Thirdparty/MurmurHash3.h) is
the link from the above Tweet.

