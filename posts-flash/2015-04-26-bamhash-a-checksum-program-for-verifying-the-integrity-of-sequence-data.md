---
title: 'BamHash: a checksum program for verifying the integrity of sequence data'
tags: []
categories:
- blog
---
[Link](http://biorxiv.org/content/early/2015/03/03/015867)
<!--more-->

> Summary: Large resequencing projects require a significant amount of storage
for raw sequences, as well as alignment files. Since the raw sequences are
redundant once the alignment has been generated, it is possible to keep only
the alignment files. We present BamHash, a checksum based method to ensure
that the read pairs in FASTQ files match exactly the read pairs stored in BAM
files, regardless of the ordering of reads. BamHash can be used to verify the
integrity of the files stored and discover any discrepancies. Thus, BamHash
can be used to determine if it is safe to delete the FASTQ files storing raw
sequencing reads after alignment, without the loss of data. Availability and
Implementation: The software is implemented in C++, GPL licensed and available
at https://github.com/DecodeGenetics/BamHash Contact pmelsted@hi.is

