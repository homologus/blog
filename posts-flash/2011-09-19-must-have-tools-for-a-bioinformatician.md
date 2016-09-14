---
title: Must-have Tools for a Bioinformatician
tags:
- bioinformatics
categories:
- blog
---
A friend of mine got so overwhelmed after receiving seven large hiSEQ
libraries (to be assembled in a week) that she deleted everything from her
hard-drive. Trying to show the bright side of things, I told her that this
would be a great opportunity to clean all clutter from her server (done :) )
and install only the top quality programs that she will use again and again.
Can you suggest some programs that you use very frequently? Here is the list I
came up with. Please feel free to add.
<!--more-->

**A. Sequence Search**

Sequence search is one of the tasks bioinformaticians do day in and out. The
purpose of those searches vary. Let me list a few here.

(i) You have a protein sequence and you want to find out whether it matches
any other protein that people have already studied.

(ii) You have a large library (100M) of Illumina reads from human genome and
you like to match them against the reference genome to find SNPs.

(iii) You have a long EST from an Arabidopsis sample and you want to find its
coordinates on the Arabidopsis genome.

(iv) You have a peptide sequence from mouse, but do not know its gene
sequence. You like to find out the gene sequence by searching the peptide
against the mouse genome.

You can see that those four examples need different capabilities from the
search program and your computer. For example, the second one can assume that
the matches will be near exact, and use that information to speed up the
search process. On the other hand, the first example cannot make that
compromise, but speed may not be an issue, when you are searching for only one
or few proteins instead of 100M.

A bioinformatician needs to have many types of search programs to fit various
purposes. Here is the core set I recommend -

**NCBI BLAST**

Purpose

This is the all-purpose sequence homlogy search program that every biologist
is familiar with. One can use BLAST to search nucleotide sequence against
protein database, nucleotide against nucleotide database, peptide against
nucleotide database or peptide against protein database.

Download from

[NCBI ftp site](ftp://ftp.ncbi.nih.gov/blast/executables/LATEST)

Installation

Installation is easy. Download the right executable for your type of computer
and nothing else needs to be done other than setting path.

Common commands

preparing database: formatdb -i [FASTA reference dbname] -p F -o T

nucl against nucl: blastall -i [FASTA seq] -d [ref dbname] -p blastn -e 1e-10
-o [output]

nucl against nucl: blastall -i [FASTA seq] -d [ref dbname] -p blastp -e 1e-10
-o [output]

nucl against nucl: blastall -i [FASTA seq] -d [ref dbname] -p blastn -e 1e-10
-o [output]

nucl against nucl: blastall -i [FASTA seq] -d [ref dbname] -p blastn -e 1e-10
-o [output]

Online references

[NCBI](http://www.ncbi.nlm.nih.gov/books/NBK1763/)

Weakness

BLAST is too slow for searching sequences that map exactly on a genome, and
especially for mapping large libraries of short reads on a reference genome.

Alternative - [HMMER](http://hmmer.janelia.org/) (claims to be far more
accurate than BLAST or FASTA for protein homology search),
[FASTA](http://fasta.bioch.virginia.edu/fasta_www2/fasta_list2.shtml). Also
note that many variations of BLAST exist, such as megaBLAST, WU-BLAST, etc.

**BLAT**

Purpose

BLAT is used for mapping a long sequence that matches a genome near exactly.

Download from

[UCSC ftp site](http://hgdownload.cse.ucsc.edu/admin/exe/)

Installation

Installation is easy. Download the right executable for your type of computer
and nothing else needs to be done other than setting path.

Common command

blat [database] [query] [output]

Online references

[UCSC](http://genome.ucsc.edu/FAQ/FAQblat.html#blat5)

Weakness

BLAT is best for mapping ESTs on a reference genome, and it reports all splice
junctions properly. Don't use it for any other purpose.

Alternative - [exonerate](http://www.ebi.ac.uk/~guy/exonerate/beginner.html)
from EBI.

**Bowtie/Tophat/Cufflink**

Purpose

Quick mapping of large number of short read sequences on a reference genome,
and constructing gene sequences.

Download from

[Bowtie website at sourceforge](http://sourceforge.net/projects/bowtie-
bio/files/bowtie/old/)

Installation

Installation is easy. Download the right executable for your type of computer
and nothing else needs to be done other than setting path.

Common command

building index: bowtie-build [reference] [index]

unpaired reads: bowtie [index] [read file] [output]

paired reads: bowtie [index] -1 [left read] -2 [right read] [output]

Online references

[Tutorial](http://bowtie-bio.sourceforge.net/tutorial.shtml)

[Manual](http://bowtie-bio.sourceforge.net/manual.shtml)

Weakness

Primarily for short reads. Requires near perfect match.

Alternatives - [BWA](http://bio-bwa.sourceforge.net/),
[MAQ](http://maq.sourceforge.net/),
[Shrimp](http://www.bioinformatics.colostate.edu/shrimp.html).

**B. Multiple Sequence Alignment**

**Clustal (clustalw2)**

Purpose

Clustal is perfect for aligning large number of similar sequences (nucleotide
or protein) and find their common segments.

Download from

[EBI ftp site](http://www.clustal.org/download/current/)

Installation

Installation is easy. Download the right executable for your type of computer
and nothing else needs to be done other than setting path.

Common command

clustalw2 [FASTA sequence]

Online references

[Clustal manual](http://www.clustal.org/download/clustalw_help.txt)

Weakness

Performs poorly, if any sequence has large N block.

Alternative - BLAST.

**C. SNP Analysis**

**Samtools**

Purpose

Samtools is the most efficient program to store and access large number of
short read alignments. SAM format has almost become a standard now.

Download from

[Sourceforge site](http://sourceforge.net/projects/samtools/files/samtools/)

Installation

Installation is easy. Download the right executable for your type of computer
and nothing else needs to be done other than setting path.

Common command

Check the synopsis section at the top of [this
page](http://samtools.sourceforge.net/samtools.shtml).

Online references

[samtools manual](http://samtools.sourceforge.net/samtools.shtml)

[samtools
FAQ](http://sourceforge.net/apps/mediawiki/samtools/index.php?title=SAM_FAQ)

Weakness

Alternative - [SOAPsnp](http://soap.genomics.org.cn/soapsnp.html).

**D. Assembly**

**CAP3**

Purpose

A very versatile assembly program, when the number of reads is not very high.

Download from

[Author's site](http://seq.cs.iastate.edu/cap3.html)

Installation

Installation is easy. Download the right executable for your type of computer.
That is all.

Common command

cap3 [fasta file]

Online references

[Documentation](http://deepc2.psi.iastate.edu/aat/cap/capdoc.html)

Weakness

This is an overlap and extend type of program. De Bruijn assemblers are better
for large library of short reads.

**Newbler**

Among all programs listed here, Newbler is the only one I never used. However,
everyone using 454 data recommends it. The software comes from Roche and
[here](http://seqanswers.com/forums/showthread.php?t=114) is how you get it in
various countries of the world. Source code is proprietary and it is not a de
Bruijn assembler.

**SOAPdenovo**

Purpose

One of the best de Bruijn assemblers around, both in terms of performance and
memory requirement.

Download from

[BGI website](http://soap.genomics.org.cn/soapdenovo.html)

Installation

Installation is easy. You can download the executable from their website.

Common command

Check [here](http://soap.genomics.org.cn/soapdenovo.html).

Online references

[BGI website for SOAPdenovo](http://soap.genomics.org.cn/soapdenovo.html)

Weakness

Source code unavailable.

**Velvet**

Purpose

De Bruijn assembler for genomic data. Works great for color space.

Download from

[EBI website](http://www.ebi.ac.uk/~zerbino/velvet/)

Installation

'make' or 'make color'

Common command

velveth out 21 -shortPaired reads.fa

velvetg out

Online references

[Manual](http://www.ebi.ac.uk/~zerbino/velvet/Manual.pdf). Also Velvet mailing
list is very active.

Weakness

Requires large RAM. Also, it is not good for transcriptome data, unless you
also use Oases.

**Oases**

Purpose

De Bruijn assembler for transcriptome that works on Velvet output.

Download from

[Oases website at EBI](http://www.ebi.ac.uk/~zerbino/oases/)

Installation

make 'VELVET_DIR=/path/to/velvet' [check manual for color space installation]

Common command

velveth out 21 -shortPaired reads.fa

velvetg out -read_trkg yes

oases out -ins_length 200

Online references -

[UCSC](http://www.ebi.ac.uk/~zerbino/oases/Manual.txt). Also, Oases mailing
list is very active.

Weakness

Needs even more RAM than Velvet.

**Trinity**

Purpose

De Bruijn assembler for transcriptome.

Download from

[sourceforge website for trinity](http://trinityrnaseq.sourceforge.net/)

Installation

You need Java in your machine. C/C++ part needs to be compiled with 'make'.
Java part is already compiled.

Common command

Trinity.sh --seqType fq --left l.fq --right r.fq --output outdir

Online references

[Trinity manual](http://trinityrnaseq.sourceforge.net/)

Weakness

Inchworm step is very slow.

Alternatives - [Abyss](http://www.bcgsc.ca/platform/bioinfo/software/abyss)
(parallel assembler for MPI machines),
[Contrail](http://sourceforge.net/apps/mediawiki/contrail-
bio/index.php?title=Contrail) (parallel assembler for hadoop),
[Euler](http://nbcr.sdsc.edu/euler/), [ALLpaths-
LG](http://www.broadinstitute.org/software/allpaths-lg/blog/).

**E. Protein Function Analysis**

**BLAST against NCBI NR**

**Interpro scan**

**F. Statistical Analysis**

**R**

**G. Microarray data**

**Bioconductor module in R**

limma package

Common commands: lmFit, eBayes, topTable

**H. Sharing and Visualization**

**IGV**

**I. Colorspace**

**ABI Color space library**

We covered all of four above topics in various posts here.

**J. Bonus tools**

**ssaha2**

**hmmer**

**Mummer**

**Stampy**

**repeatmasker**

**Hadoop**

\-----------------------

Here are few places I go to to find information on latest software packages -

i) [Seqanswers Wiki](http://seqanswers.com/wiki/Software/list)

ii) [Bioinformatics tools at EBI](http://www.ebi.ac.uk/Tools/)

iii) List of [all resources at NCBI](http://www.ncbi.nlm.nih.gov/guide/all/),
and [sub list of bioinformatic
tools](http://www.ncbi.nlm.nih.gov/guide/all/#tools_).

iv) [Computational tools at BROAD institute](http://www.broadinstitute.org
/scientific-community/science/programs/genome-sequencing-and-analysis
/computational-rd/computational-)

v) [Software tools from UCSC](http://genome.ucsc.edu/util.html).

