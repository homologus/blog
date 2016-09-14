---
title: Bioinformatics One-liners
tags: []
categories:
- blog
---
Stephen Turner [maintains a very useful list of one-liner commands at
github](https://github.com/stephenturner/oneliners).
<!--more-->

>

Basic awk & sed

Extract fields 2, 4, and 5 from file.txt:

awk '{print $2,$4,$5}' input.txt

Print each line where the 5th field is equal to abc123:

awk '$5 == "abc123"' file.txt

Print each line where the 5th field is not equal to abc123:

awk '$5 != "abc123"' file.txt

Print each line whose 7th field matches the regular expression:

awk '$7 ~ /^[a-f]/' file.txt

Print each line whose 7th field does not match the regular expression:

awk '$7 !~ /^[a-f]/' file.txt

Get unique entries in file.txt based on column 1 (takes only the first
instance):

awk '!arr[$2]++' file.txt

Print rows where column 3 is larger than column 5 in file.txt:

awk '$3>$5' file.txt

Sum column 1 of file.txt:

awk '{sum+=$1} END {print sum}' file.txt

Compute the mean of column 2:

awk '{x+=$2}END{print x/NR}' file.txt

Number each line in file.txt:

sed = file.txt | sed 'N;s/\n/ /'

Replace all occurances of foo with bar in file.txt:

sed 's/foo/bar/g' file.txt

Trim leading whitespace in file.txt:

sed 's/^[ \t]*//' file.txt

Trim trailing whitespace in file.txt:

sed 's/[ \t]*$//' file.txt

Trim leading and trailing whitespace in file.txt:

sed 's/^[ \t]*//;s/[ \t]*$//' file.txt

Delete blank lines in file.txt:

sed '/^$/d' file.txt

awk & sed for bioinformatics

Returns all lines on Chr 1 between 1MB and 2MB in file.txt. (assumes)
chromosome in column 1 and position in column 3 (this same concept can be used
to return only variants that above specific allele frequencies):

cat file.txt | awk '$1=="1"' | awk '$3>=1000000' | awk '$3<=2000000'

Basic sequence statistics. Print total number of reads, total number unique
reads, percentage of unique reads, most abundant sequence, its frequency, and
percentage of total in file.fq:

cat myfile.fq | awk '((NR-2)%4==0){read=$1;total++;count[read]++}END{for(read
in count){if(!max||count[read]>max)
{max=count[read];maxRead=read};if(count[read]==1){unique++}};print total,uniqu
e,unique*100/total,maxRead,count[maxRead],count[maxRead]*100/total}'

Convert .bam back to .fastq:

samtools view file.bam | awk 'BEGIN {FS="\t"} {print "@" $1 "\n" $10 "\n+\n"
$11}' > file.fq

Keep only top bit scores in blast hits (best bit score only):

awk '{ if(!x[$1]++) {print $0; bitscore=($14-1)} else { if($14>bitscore) print
$0} }' blastout.txt

Keep only top bit scores in blast hits (5 less than the top):

awk '{ if(!x[$1]++) {print $0; bitscore=($14-6)} else { if($14>bitscore) print
$0} }' blastout.txt

Split a multi-FASTA file into individual FASTA files:

awk '/^>/{s=++d".fa"} {print > s}' multi.fa

Convert a FASTQ file to FASTA:

sed -n '1~4s/^@/>/p;2~4p' file.fq > file.fa

Extract every 4th line starting at the second line (extract the sequence from
FASTQ file):

sed -n '2~4p' file.fq

sort, uniq, cut, etc.

You can read the rest [here at
github](https://github.com/stephenturner/oneliners). Also, Stephen Turner
[wrote a blog post](http://gettinggeneticsdone.blogspot.com/2013/10/useful-
linux-oneliners-for-bioinformatics.html) providing nice introduction to the
list.

