---
title: Comparison of Sequencing Instruments (Wish they Included PacBio)
categories:
- chem
---
[Here](http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjournal.pone.0067
539) is a good paper comparing various sequencing technologies and options.
Wish they included PacBio. They have an interesting chart comparing k-mer
frequencies from various technologies. That method will not work with PacBio
however, because very few 31-mers stay intact with 85% indel rate in PacBio.
<!--more-->

**Abstract**

> The fully annotated genome sequence of the European strain, 26695 was first
published in 1997 and, in 1999, it was directly compared to the USA isolate
J99, promoting two standard laboratory isolates for Helicobacter pylori (H.
pylori) research. With the genomic scaffolds available from these important
genomes and the advent of benchtop high-throughput sequencing technology, a
bacterial genome can now be sequenced within a few days. We sequenced and
analysed strains J99 and 26695 using the benchtop-sequencing machines Ion
Torrent PGM and the Illumina MiSeq Nextera and Nextera XT methodologies. Using
publically available algorithms, we analysed the raw data and interrogated
both genomes by mapping the data and by de novo assembly. We compared the
accuracy of the coding sequence assemblies to the originally published
sequences. With the Ion Torrent PGM, we found an inherently high-error rate in
the raw sequence data. Using the Illumina MiSeq, we found significantly more
non-covered nucleotides when using the less expensive Illumina Nextera XT
compared with the Illumina Nextera library creation method. We found the most
accurate de novo assemblies using the Nextera technology, however, extracting
an accurate multi-locus sequence type was inconsistent compared to the Ion
Torrent PGM. We found the cagPAI failed to assemble onto a single contig in
all technologies but was more accurate using the Nextera. Our results indicate
the Illumina MiSeq Nextera method is the most accurate for de novo whole
genome sequencing of H. pylori.

The paper also mentioned observing different GC-content from different
technologies.

> Unique 31-mers in the output sequence data are expected to be errors given
there is adequate depth to cover each genome more than 50-times. To determine
if these mapped unique 31-mers were similar in GC content to highly covered
regions, we compared their GC content to 105, randomly chosen, highly frequent
31-mers (occurring at a frequency between 20 and 50). This analysis may
provide insights as to the reason for the low coverage. We found significant
differences in GC content across all sequencing technologies and library
preparation methods (Figure S4 and Table 2). The GC content of the Ion Torrent
mapped unique reads was significantly higher for both genomes, suggesting a
technical reason for the lack of coverage. Interestingly, the GC content of
unique 31-mers that map to the reference genomes derived by the Illumina
library preparation methods (Nextera and Nextera XT) identified conflicting
results.

