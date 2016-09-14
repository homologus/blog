---
title: Format of Velvet Output File 'Roadmaps'
tags:
- velvet
- Roadmap
categories:
- blog
---
If you used Velvet genome assembler, you possibly have noticed a file named
'Roadmaps' being created by the 'velveth' program.
[Here](http://listserver.ebi.ac.uk/pipermail/velvet-
users/2011-January/001230.html) is a brief explanation of the format of
'Roadmap' file explained by Daniel Zerbino, the author of Velvet.
<!--more-->

>

The Roadmap file is not normally meant to be parsed by the user, it is

simply internal to velvet.

However, if you really want to know the format is:

ROADMAP $query_id

$target_id $prev_kmers $target_start $target_finish

etc.

Where:

$target_id is negative if on reverse strand

[ $target_start, $target_finish [ is the domain of the target sequence

being aligned (note that it is inclusive at the start and exclusive at

the finish)

$prev_kmers is the number of unaligned k-mers in the query sequence

before the alignment to the target (note in the examples below how this

value does not necessarily change from alignment to alignment, this

means that they are contiguous on the query.)

Real simple? It will be in a minute.

Let us take a really small library with only two reads. Here are the reads -

![](http://www.homolog.us/blogs/wp-content/uploads/2011/12/Capture11.png)

Two overlapping regions between the reads are shown with yellow shade and red
underline.

Here is the 'Roadmaps' file generated with k=21. The first line reports the
total number of reads in the first column and k-mer size in the third column.
We have not figured out what the second and fourth columns mean.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/12/Capture2.png)

Let us now explain the rest of the 'Roadmaps' file. Each line beginning with
'ROADMAP' covers a read. We have two reads. Therefore, you see 'ROADMAP 1' and
ROADMAP 2'. In addition, the file has two non-ROADMAP files.

To understand the non-ROADMAP lines, think about what 'velveth' does. It goes
through all reads one by one and makes a catalog of all unique k-mers present
in them. With k=21, it scans through the first read ('ROADMAP 1') and does not
see any repeating 21-mer within the read. Moreover, since it is the first
read, there is no prior history to be compared with. So, nothing is written
after 'ROADMAP 1' line.

Then, velveth scans the second read ('ROADMAP 2') and sees various 21-mers
that were already present in the first read. Velveth also find those repeating
21-mers to be grouped into two regions (red underline and yellow shade). It
reports those two overlapping regions in two subsequent lines of Roadmaps
file.

Let us now explain the four columns of those reporting lines. The first column
reports which ROADMAP a duplicated segment overlaps with. For ROADMAP 2, both
duplicates are with ROADMAP 1. Therefore, the first column is 1 for both
entries.

Second column reports the coordinate in 'ROADMAP 2', where the overlap starts
based on a start=0 convention. Third and fourth columns report the start and
stop of overlapping k-mers in 'ROADMAP 1'. Note that it reports end point of
the k-mer, not the actual duplicate segment. Therefore, the last coordinate
changes with the length of k-mer.

As an example, the second reporting line has four entries - '1 55 0 5'. It
means ROADMAP 2 has a 21-mer overlap with ROADMAP 1 (first column). The
overlap starts from coordinate 55 of ROADMAP 2 (second column) and coordinate
0 of ROADMAP 1 (third column). The overlap is 5 nucleotides or rather 5 k-mers
long (fourth column). Based on the above information, you can see that the
line refers to the yellow shaded region. The real length of the yellow shaded
region is (column 4 + k-mer size -1)=5 +21 -1=25 nucleotides. The real length
of the red underlined region is 46+21-1=66 nucleotides.

Let us try the same example with k=31. With k=31, there is only one
overlapping region between the two reads longer than the k-mer size. Here is
the 'Roadmaps' output.

![](http://www.homolog.us/blogs/wp-content/uploads/2011/12/Capture3.png)

Here are two fun exercises that will help you understand the format of
'Roadmaps' file even better. Please try these -

i) Run the same example with kmer size=1.

ii) Replace second read with its reverse complement and run velveth with k=21.

