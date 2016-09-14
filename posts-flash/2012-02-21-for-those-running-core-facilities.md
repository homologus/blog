---
title: For those Running Core Facilities
tags: []
categories:
- blog
---
[A quick note - We edited yesterday's commentary and added two 'rules' to
simplify bioinformatic analysis. If you follow the rules as a pre-processing
step, you will not have to think about strandedness of the reads in the rest
of the analysis.]
<!--more-->

Over the last few months, we discussed various topics ranging from
transcriptomics, assembly algorithms, hardware technologies such as Hadoop,
color space data, etc. Today we like to take a step back to go over the entire
forest of NGS bioinformatics. Although the headline of this topic mentions
those running core facilities, the following discussions should be helpful for
anyone planning and performing analysis of NGS data. Mostly they are provided
as food for thought and not definitive answers. Please feel free to share your
experience in the comment section.

**Choice of Sequencing Technology**

Often the choice of sequencing technology (454, Illumina, ABI SOLiD, etc.) is
done solely based on the amount of sequence to be available along with cost
per base. In our opinion, four factors should be taken into consideration -

(i) Sequencing volume and cost per base,

(ii) Length of individual reads (**after removing low quality tails**),

(iii) Maximum possible insert size for mate-paired reads,

(iv) Quality of reads.

Regarding the second factor, people often talk about 75nt reads versus 65nt
reads, but if stretching the technology for higher read length results in many
erroneous bases (typically near 3' end), it may be better to stick with
shorter reads.

Factor (iii) is especially important for assembling reads. After the small
contigs from a library are assembled locally, their placement on larger
scaffolds depend on distances between mate pairs. Therefore, it is more cost-
effective to push for higher distance between read pairs than using
technologies with longer read sizes.

A fifth factor - availability of software tools - often gets mentioned in
choice of sequencing technology. This issue becomes important for color space
data from ABI SOLiD, because most new programs are written and tested for
nucleotide space data before the color space versions become available. We
believe if a new technology wins on (i-iv), software gap gets filled in a
reasonable time. In fact, a technology superior on (i-iv) eventually becomes
the platform of choice for new developers, and those with other technologies
need to catch up. Our biggest complaint about SOLiD data is with (iv). Those
machines churn out an order of magnitude more data than typical Illumina
instrument, but the reads contain significant amount of 'color space noise'
and other errors. It is true that 'color space noise' can be cleaned and
ignored for mapping analysis, but it adds a layer of complexity for assembly-
type problems, where correct and incorrect bases are not known a priori.

**Choice of computer hardware**

Two types of analysis are done on NGS data - mapping (if reference genome
exists) and assembly (if reference genome does not exist). Assembly problem is
more challenging, and requires more powerful computers.

The simplest and **most expensive** solution is to buy a computer with large
amount of RAM. This solution does not scale well for mammalian-sized genomes,
and researchers look for two alternatives -

(i) Torque-based distributed systems (distributed computing over many machines
sharing one file system),

(ii) Hadoop-based distributed systems (distributed computing over many
machines with distributed file system).

A third option being pursued by the community is to design better algorithms
(Bowtie, String Graph Assembler etc.), so that more computing can be done with
the same amount of RAM. From a strictly technical viewpoint, it is true that
those better algorithms can be further scaled using distributed computing
(Torque or Hadoop). From a practical viewpoint, writing code for different
computing architectures relies primarily on the interests of the developer
working on the algorithm. Everyone is not an expert on every technology and
can do only so much in his limited time, given that coming up with new
algorithm itself is a Herculean task. Add the complexity related to color-
space data.

In this space, we are trying to provide information so that these technology
gaps can be easily closed.

**Network bandwidth and Storage**

The network needs to be designed properly, if we plan to move gigabytes to
terabytes of data between computers. When the transfer is being done between
institutions or organizations, it appears that no network is fast enough and
people are resorting to low tech solutions such as simply [mailing the disks
through postal service](http://www.labnol.org/internet/offsite-backup-from-
amazon/8729/).

Storage, and especially backup storage, is another important factor to pay
attention to. We suggest copies of primary data, code and important secondary
(derived) files, to be stored off-site to avoid natural calamities and machine
failure. It is true that earthquakes do not happen very frequently, but hard-
drive crashes and file corruption are often the ways of life for someone
dealing with large volume of data.

We will finish the above discussion by covering the following three topics in
the next commentary -

**Algorithms for Low Level Analysis**

**Algorithms for High Level Analysis**

**Presenting and Accessing the Data**

