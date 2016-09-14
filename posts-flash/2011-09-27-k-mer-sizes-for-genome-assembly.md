---
title: K-mer Sizes for Genome Assembly
tags:
- ABI-SoLID
- de-bruijn
- K-mer
- genome assembly
- color space
categories:
- blog
---
De Bruijn assemblers like Velvet, Trinity, etc. use K-mers of odd length
(21,23,25...). Here is the rationale. If K-mers are of even length, some
K-mers can be reverse complements of themselves (e.g. ATATATATATAT). That will
create ambiguity in the de Bruijn graph and make its resolution difficult.
Palindromic K-mers can be always avoided with odd K-mer size, because the
reverse complement of center nucleotide is different from the nucleotide
itself.
<!--more-->

In color space, reverse complement of a sequence is the reverse of the
sequence. That means some odd-sized K-mers can be self-complementary, whereas
even sized K-mers can never be so except for sequences like 111111111,
2222222, 3333333 and 44444444.

