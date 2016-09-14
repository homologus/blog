---
title: GPU and FPGA-accelerated Bioinformatics Algorithms
tags: []
categories:
- blog
---
Many researchers are starting to look into hardware acceleration to speed up
their bioinformatics analysis. For example, [please check this seqanswers
thread](http://seqanswers.com/forums/showthread.php?t=30353), where davispeter
asked about GPU-accelerated genome assembly programs.
<!--more-->

Our next few commentaries will cover various hardware-accelerated approaches.
We will start from very basics before exploring more complex topics. Following
our typical style, we will stay away from describing how to download, install
and run specific programs and instead focus on explaining how the technologies
work and discussing programming approach and algorithms. We will also try to
explain, where the main cost savings come from. Be aware the topic of cost
savings is directly related to ease of programming, but 'ease of programming'
is often very subjective. My grandma finds it very difficult to program her
microwave clock.

Please feel free to suggest any algorithm of your interest in the comment
section. We are collecting a list of references and will append to this post,
as soon as it is ready.

\-------------------------

**GPU Algorithms**

1\. Short Read Alignment

[CUSHAW - fast short read alignment for CUDA-enabled
GPUs](http://cushaw.sourceforge.net/homepage.htm#latest)

Yongchao Liu, Bertil Schmidt, and Douglas L. Maskell: " CUSHAW: a CUDA
compatible short read aligner to large genomes based on the Burrows-Wheeler
transform". Bioinformatics, 2012, 28(14): 1830-1837.

Yongchao Liu and Bertil Schmidt: "Long read alignment based on maximal exact
match seeds". Bioinformatics, 2012, 28(18): i318-324.

[Exact and complete short read alignment to microbial genomes using GPU
programming - Jochen Blom et al.](http://bioinformatics.oxfordjournals.org/con
tent/early/2011/03/30/bioinformatics.btr151.full.pdf)

2\. Efficient Hash Tables on the GPU

[PhD Thesis - UC
Davis](http://idav.ucdavis.edu/~dfalcant//downloads/dissertation.pdf)

[Dan Alcantara's
Website](http://idav.ucdavis.edu/~dfalcant/research/hashing.php)

3\. Assembly

Yongchao Liu, Bertil Schmidt, and Douglas L. Maskell: "Parallelized short read
assembly of large genomes using de Bruijn graphs". BMC Bioinformatics 2011,
12:354.

4\. Error Correction

Yongchao Liu, Bertil Schmidt, and Douglas L. Maskell: "DecGPU: distributed
error correction on massively parallel graphics processing units using CUDA
and MPI". BMC Bioinformatics (impact factor 3.43), 2011, 12:85.

5\. Phylogeny

[Efficient Implementation of MrBayes on multi-GPU - Jie Bao, Hongju Xia,
Jianfu Zhou, Xiaoguang Liu and Gang
Wang.](http://mbe.oxfordjournals.org/content/early/2013/03/14/molbev.mst043)

[MrBayes on a graphics processing unit - Zhou J, Liu X, Stones DS, Xie Q, Wang
G.](http://www.ncbi.nlm.nih.gov/pubmed/21414986)

6\. BLAST

[GPU-BLAST: using graphics processors to accelerate protein sequence alignment

Panagiotis D. Vouzis and Nikolaos V. Sahinidis.

8\. Other Implemented Programs

[NVIDIA's GPU page.](http://www.nvidia.com/object/bio_info_life_sciences.html)

\------------------------

**FPGA Algorithms**

1\. Short Read Alignment

[Shepard: A Fast Exact Match Short Read
Aligner](http://rcl.ece.iastate.edu/sites/default/files/papers/NelTow12A.pdf)

[An FPGA Acceleration of Short Read Human Genome Mapping - Corey Bruce Olson](
http://www.ee.washington.edu/faculty/hauck/publications/ShortRead_MS.pdf)

[A hybrid short read mapping accelerator - Yupeng Chen, Bertil Schmidt and
Douglas L Maskell.](http://www.biomedcentral.com/1471-2105/14/67)

[Accelerating Phylogeny-Aware Short DNA Read Alignment with FPGAs- Nikolaos
Alachiotis, Simon Berger, Alexandros
Stamatakis](http://sco.h-its.org/exelixis/pubs/Exelixis-RRDR-2011-3.pdf)

2\. BLAST

[RC-BLAST: Towards a Portable, Cost-Effective Open Source Hardware

Implementation - Krishna Muriki et al.

[Single Pass, BLAST-Like, Approximate String Matching on FPGAs - Martin C.
Herbordt Josh Model Yongfeng Gu Bharat Sukhwani Tom
VanCourt.](http://www.bu.edu/caadlab/FCCM06_blast.pdf)

[A Systolic Array-Based FPGA Parallel Architecture for the BLAST Algorithm -
Xinyu Guo, HongWang, and Vijay
Devabhaktuni.](http://www.hindawi.com/isrn/bioinformatics/2012/195658/)

\------------------

**MPI, Multicore**

1\. BLAST

[The Design, Implementation, and Evaluation of mpiBLAST](http://www.scc.acad.b
g/ncsa/downloads/inst_adapt/mpiBLAST/The%20Design,%20Implementation,%20and%20E
valuation%20of%20mpiBLAST.pdf)

2\. Burrows Wheeler

[Optimizing Burrows-Wheeler Transform-Based Sequence Alignment on Multicore
Architectures - Jing Zhang et
al.](http://www.mcs.anl.gov/~balaji/pubs/2013/ccgrid/ccgrid13.bwa.pdf)

