---
title: Building an NGS Reference List (de novo assembly category)
tags: []
categories:
- blog
---
Did we miss any important category/paper?
<!--more-->

Not all t's are crossed and i's are dotted yet. We will also add hyperlinks
soon.

We created this list for our own convenience. However, it took us some time to
get all the pieces together, and we thought posting the full list here would
help someone else go to sleep early. Wherever we could, we added short
narration about the papers or the section (again for our own convenience).
There is no guarantee that the texts describe the papers accurately. Neither
is there guarantee that the texts describe the papers inaccurately.

The papers mentioned here are related to bioinformatics problems, when no
reference genome exists. We split the other set of papers with alignment, SNP
calling, etc. into another set.

**1\. Pre-NGS Genome Assemblers**

This section includes old assembly-related papers that we may need to cite
from time to time. The first subgroup has links to base-calling and error
correction programs such as phred, phrap and consed. The second subgroup has
more sophisticated assemblers, but they mostly belong to overlap-layout-
consensus type. Those dinosaurs used to rule over the world in not too distant
past.

CAP3 and Celere are the only programs that we like. They are our pet
dinosaurs. That does not mean the others are bad. We heard very good opinions
about them from, well, the genome centers that nurture them. Most programs are
associated with one or other genome centers. TIGR is from TIGR. ARACHNE
belongs to Broad. Phusion is from EMBL. Atlas came from Baylor. Celera was
written by J. C. Venter's company, but is maintained by the bioinformatics
group from Maryland.

**Base-calling and error detection**

Krawetz SA (1989) **Sequence errors described in GenBank: a means to determine
the accuracy of DNA sequence interpretation.**_Nucleic Acids Res_.
17(10):3951-7. [Link](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC317871/)

Bonfield JK, Staden R (1995) **The application of numerical estimates of base
calling accuracy to DNA sequencing projects.**_Nucleic Acids Res._
23(8):1406-10.
[Link](http://nar.oxfordjournals.org/content/23/8/1406.abstract)

Ewing B, Hillier L, Wendl M, Green P: **Basecalling of automated sequencer
traces using phred. I. Accuracy assessment.**_Genome Research_ 8:175-185
(1998). [Link](http://www.ncbi.nlm.nih.gov:80/entrez/query.fcgi?cmd=Retrieve&d
b=pubmed&dopt=Abstract&list_uids=9521921)

Ewing B, Green P: **Base calling of automated sequencer traces using phred.
II. Error probabilities.**_Genome Research_ 8:186-194 (1998). [Link](http://ww
w.ncbi.nlm.nih.gov:80/entrez/query.fcgi?cmd=Retrieve&db=pubmed&dopt=Abstract&l
ist_uids=9521922)

Gordon D, Abajian C, Green P: (1998) **Consed: a graphical tool for sequence
finishing.**_Genome Research_ 8:195-202 [Link](http://www.ncbi.nlm.nih.gov/ent
rez/query.fcgi?holding=npg&cmd=Retrieve&db=PubMed&list_uids=9521923&dopt=Abstr
act)

**Assembler**

Sutton, G. G., White, O., Adams, M. D., Kerlavage, A. R. (1995) **TIGR
Assembler: A new tool for assembling large shotgun sequencing
projects.**_Genome Science and Technology._ 1(1): 9-19. [Link](http://www.jcvi
.org/cms/publications/listing/abstract/browse/123/article/tigr-assembler-a
-new-tool-for-assembling-large-shotgun-sequencing-
projects/?tx_ttnews\[backPid\]=569&cHash=911b359883)

Huang X, Madan A, (1999) **CAP3: A DNA sequence assembly program.**_Genome
Res._ 9(9):868-77. [Link](http://genome.cshlp.org/content/9/9/868.long)

Myers EW, Sutton GG, Delcher AL, Dew IM, Fasulo DP, Flanigan MJ, Kravitz SA,
Mobarry CM, Reinert KHJ, Remington KA, _et al_.: (2000) **A whole-genome
assembly of Drosophila. **_Science_**287**(5461)**:**2196-2204\.
**[Link](http://www.sciencemag.org/content/287/5461/2196.abstract)**

Batzoglou S, Jaffe DB, Stanley K, Butler J, Gnerre S, Mauceli E, Berger B,
Mesirov JP, Lander ES: (2002) **ARACHNE: A whole-genome shotgun assembler.
**_Genome Res_**12**(1)**:**177-189.
[Link](http://genome.cshlp.org/content/12/1/177.long)

Mullikin JC, Ning ZM: (2003) **The phusion assembler. **_Genome
Res_**13**(1)**:**81-90. [Link](http://genome.cshlp.org/content/13/1/81.long)

Istrail, S. et al. (2004) **Whole-Genome Shotgun Assembly and Comparison of
Human Genome Assemblies.** Proc. Nat. Acad. Sci. USA 101:1916-1921.
[Link](http://www.pnas.org/content/101/7/1916.abstract)

David B. Jaffe, Jonathan Butler, Sante Gnerre, Evan Mauceli, Kerstin Lindblad-
Toh,Jill P. Mesirov, Michael C. Zody,and Eric S. Lander (2003) **Whole-Genome
Sequence Assembly for Mammalian Genomes: Arachne 2 **_Genome Res._ 13(1):
9196. [Link](http://genome.cshlp.org/content/13/1/91.long)

Havlak P, Chen R, Durbin KJ, Egan A, Ren YR, Song XZ, Weinstock GM, Gibbs RA
(2004) **The atlas genome assembly system. **_Genome
Res_**14**(4)**:**721-732. [Link](http://Link/)

Chapman JA, Ho I, Sunkara S, Luo S, Schroth GP, et al. (2011) **Meraculous:
**_**De Novo**_** Genome Assembly with Short Paired-End Reads.**_PLoS ONE_
6(8): e23501. [Link](http://www.plosone.org/article/info%3Adoi%2F10.1371%2Fjou
rnal.pone.0023501#pone.0023501.s003)

Mihai Pop, Adam Phillippy, Arthur L. Delcher, Steven L. Salzberg (2004)
**Comparative Genome Assembly**, _Briefings in Bioinformatics_ 5 (3):237-248.
[Link](http://bib.oxfordjournals.org/content/5/3/237.abstract)

R. Xia and A. Kim (2012) **MERmaid: A Parallel Genome Assembler for the
Cloud.**[Link](http://Link/)

Weber JL, Myers EW (1997) **Human whole-genome shotgun sequencing.** Genome
Res 7: 401409. [Link](http://Link/)

**2\. NGS Genome Assemblers**

**non de Bruijn, k-mer based**

You need a video to understand this category ([pay attention to the guys, who
jumped early](http://Link/)).

Sundquist A, Ronaghi M, Tang HX, Pevzner P, Batzoglou S: (2007) **Whole-Genome
Sequencing and Assembly with High-Throughput, Short-Read Technologies. **_PLoS
ONE_, **2**(5)**. ****[Link](http://Link/)**

Warren RL, Sutton GG, Jones SJM, Holt RA: **Assembling millions of short DNA
sequences using SSAKE. **_Bioinformatics_ 2007, **23**(4)**:**500-501.
[Link](http://bioinformatics.oxfordjournals.org/content/23/4/500.full)

SHORTY (Chen and Skiena, 2007) [specialised in localising the use of paired-
end reads.]

**Daniel D Sommer**, **Arthur L Delcher**, **Steven L Salzberg******and **Mihai Po (2007) ****Minimus: a fast, lightweight genome assembler **_BMC Bioinformatics_ 2007, **8**:64. [Link](http://www.biomedcentral.com/1471-2105/8/64)

**de Bruijn graph-based assemblers**

Many articles in our blog explained this class of assemblers.

Idury RM, Waterman MS (1995) **A new algorithm for DNA sequence assembly.** J
Comput Biol 2: 291306. [Link](http://Link/)

Pevzner, Pavel A.; Tang, Haixu (2001). **Fragment Assembly with Double-
Barreled Data.** Bioinformatics/ISMB 1: 19. [Link](http://bioinformatics.oxfor
djournals.org/content/17/suppl_1/S225.abstract)

Chaisson M, Pevzner P, Tang H (2004) **Fragment assembly with short reads.**
Bioinformatics 20: 2067-74.
[Link](http://bioinformatics.oxfordjournals.org/content/20/13/2067.abstract)

Pevzner PA, Tang H, Waterman MS: **An Eulerian path approach to DNA fragment
assembly. **_Proc. Nat. Acad. Sci. USA_ 2001, **98**(17)**:**9748-9753.
[Link](http://www.pnas.org/content/98/17/9748.abstract)

Zerbino DR, Birney E: **Velvet: Algorithms for de novo short read assembly
using de Bruijn graphs. **_Genome Research_ 2008, **18**(5)**:**821-829.
[Link](http://genome.cshlp.org/content/18/5/821)

Zerbino, D., Genome assembly and comparison using de Bruijn graphs Ph.D.
Thesis, EBI, UK.
[Link](http://www.ebi.ac.uk/training/ftp/PhDtheses/Daniel_Zerbino.pdf)

Butler J, MacCallum I, Kleber M, Shlyakhter IA, Belmonte MK, Lander ES,
Nusbaum C, Jaffe DB: **ALLPATHS: De novo assembly of whole-genome shotgun
microreads. **_Genome Research_ 2008, **18**(5)**:**810-820.
[Link](http://genome.cshlp.org/content/18/5/810.long)

Simpson JT, Wong K, Jackman SD, Schein JE, Jones SJ, Birol I: **ABySS: A
parallel assembler for short read sequence data. **_Genome Research_ 2009,
**19**(6)**:**1117-1123.
[Link](http://genome.cshlp.org/content/19/6/1117.long)

Boisvert S, Laviolette F, Corbeil J. J Comput Biol. (2010) **Ray: simultaneous
assembly of reads from a mix of high-throughput sequencing technologies.**
Nov;17(11):1519-33. Epub 2010 Oct 20.
[Link](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3119603/?tool=pubmed)

**Applications**

Li R, Zhu H, Ruan J, Qian W, Fang X, Shi Z, Li Y, Li S, Shan G, Kristiansen K,
Li S, Yang H, Wang J, Wang J (2010) **De novo assembly of human genomes with
massively parallel short read sequencing. **_Genome
Research_**20**(2)**:**265-272.
[Link](http://genome.cshlp.org/content/early/2009/12/16/gr.097261.109)

Li R, Fan W, Tian G, _et al_. (2010) **The sequence and de novo assembly of
the giant panda genome. **_Nature_**463 **(7279)**:**311-317.
[Link](http://www.nature.com/nature/journal/v463/n7279/full/nature08696.html)

Gnerre S, MacCallum I, Przybylski D, Ribeiro FJ, Burton JN, Walker BJ, Sharpe
T, Hall G, Shea TP, Sykes S, _et al_. (2011) **High-quality draft assemblies
of mammalian genomes from massively parallel sequence data. **_P Natl Acad Sci
USA_**108**(4)**:**1513-1518.
[Link](http://Linkwww.pnas.org/content/early/2010/12/20/1017351108.abstract)

Chitsaz H, Yee-Greenbaum J, Tesler G, Lombardo M, Dupont C, et al. (2011)
**Efficient de novo assembly of single-cell bacterial genomes from short-read
data sets.** Nat Biotechnol 29: 915-21.
[Link](http://www.nature.com/nbt/journal/v29/n10/full/nbt.1966.html)

Rodrigue S, Malmstrom R, Berlin A, Birren B, Henn M, et al. (2009) Whole
genome amplication and de novo assembly of single bacterial cells. PLoS One 4:
e6864.
[Link](http://www.plosone.org/article/info:doi/10.1371/journal.pone.0006864)

Schuster SC, Miller W, Ratan A, Tomsho LP, Giardine B, et al. (2010)
**Complete Khoisan and Bantu genomes from southern Africa.**_Nature_ 463:
943947. [Link](http://Link/)

**Comparison**

Deng HW, Lin Y, Li J, Shen H, Zhang L, Papasian CJ (2011) **Comparative
studies of de novo assembly tools for next-generation sequencing technologies.
**_Bioinformatics_**27**(15)**:**2031-2037. [Link](http://bioinformatics.oxfor
djournals.org/content/early/2011/06/02/bioinformatics.btr319.abstract)

Salzberg SL, Phillippy AM, Zimin AV, Puiu D, Magoc T, Koren S, Treangen T,
Schatz MC, Delcher AL, Roberts M, _et al_. (2011) **GAGE: A critical
evaluation of genome assemblies and assembly algorithms. **_Genome Res_.
[Link](http://Link/)

Zhang WY, Chen JJ, Yang Y, Tang YF, Shang J, Shen BR (2011) **A Practical
Comparison of De Novo Genome Assembly Software Tools for Next-Generation
Sequencing Technologies. **_PLoS ONE, _**6**(3)**. ****[Link](http://www.ploso
ne.org/article/info:doi%2F10.1371%2Fjournal.pone.0017915)**

Mago? T, Salzberg SL (2011) **FLASH: Fast Length Adjustment of Short Reads to
Improve Genome Assemblies. **_Bioinformatics._ [Link](http://bioinformatics.ox
fordjournals.org/content/early/2011/09/07/bioinformatics.btr507.abstract)

Salzberg SL, Kurtz S, Phillippy A, Delcher AL, Smoot M, Shumway M, Antonescu C
(2004) **Versatile and open software for comparing large genomes. **_Genome
Biol_, **5**(2)**. ****[Link](http://genomebiology.com/2004/5/2/r12)**

D. Earl et al. (2011)** Assemblathon 1: A competitive assessment of de novo
short read assembly methods, **Genome Research, 21:2224-2241.
[Link](http://genome.cshlp.org/content/21/12/2224)

**3\. Exomes, Transcriptomes, Metagenomes and Highly Polymorphic Genomes**

**Transcriptome Assemblers**

Robertson D, Schein J, Chiu R, Corbett R. Field M et al. (2010) _**De
novo**_** assembly and analysis of RNA-seq data** Nature Methods 7, 909912.
[Link](http://www.ncbi.nlm.nih.gov/pubmed/20935650)

Grabherr MG, Haas BJ, Yassour M, Levin JZ, Thompson DA et al. (2011) **Full-
length transcriptome assembly from RNA-seq data without a reference genome.
**Nat Biotechnol. 29(7):644-52. [Link](http://Link/)

Schulz M, Zerbino D, Vingron M, Birney E (2012) **Oases: robust de novo rna-
seq assembly across the dynamic range of expression levels.** Bioinformatics
28: 1086-92. [Link](http://bioinformatics.oxfordjournals.org/content/early/201
2/02/24/bioinformatics.bts094/suppl/DC1)

**Metagenomes**

Namiki T, Hachiya T, Tanaka H, Sakakibara Y (2011) **MetaVelvet: An extension
of Velvet assem-bler to de novo metagenome assembly from short sequence
reads.** ACM Conference on Bioinformatics, Computational Biology and
Biomedicine. [Link](http://dl.acm.org/citation.cfm?id=2147818&dl=ACM&coll=DL&C
FID=103502584&CFTOKEN=63007660)

Peng Y, Leung H, Yiu S, Chin F (2011) **Meta-idba: a de novo assembler for
metagenomic data. **Bioinformatics 27: i94-101.
[Link](http://bioinformatics.oxfordjournals.org/content/27/13/i94.full)

Vaughn Iverson, Robert M. Morris, Christian D. Frazar, Chris T. Berthiaume,
Rhonda L. Morales, E. Virginia Armbrust (2012) **Untangling Genomes from
Metagenomes: Revealing an Uncultured Class of Marine Euryarchaeota**, Science
335(6068):587-590.
[Link](http://www.sciencemag.org/content/335/6068/587.abstract)

C. T. B. on scaling metagenome

**Polymorphic Genomes**

Iqbal Z, Caccamo M, Turner I, Flicek P, McVean G (2012) **De novo assembly and
genotyping of variants using colored de bruijn graphs.** _Nat Genet_ 44:
226-32.
[Link](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3272472/?tool=pubmed)

S. Huang et al. (2012) **HaploMerger: Reconstructing allelic relationships for
polymorphic diploid genome assemblies, **_Genome Research. _[Link](http://geno
me.cshlp.org/content/early/2012/05/03/gr.133652.111.abstract)

**Targeted Assembly**

P. Peterlongo and R. Chikhi** (2011) Mapsembler, targeted and micro assembly
of large NGS datasets on a desktop computer **_BMC Bioinformatics_ 2012,
**13**:48. [Link](http://www.biomedcentral.com/1471-2105/13/48/abstract)

Ren L. Warren Robert A. Holt (2011)** Targeted Assembly of Short Sequence
Reads PLOS ONE.
**[Link](http://www.plosone.org/article/info:doi/10.1371/journal.pone.0019816)

**4\. Faster, better, cheaper**

**k-mer counting**

Bloom BH (1974) **Space/time trade-offs in hash coding with allowable errors.
**_Commun ACM_, **13:**422-426. [Link](http://Link/)

Marais G, Kingsford C (2011) **A fast, lock-free approach for efficient
parallel counting of occurrences of k-mers. **_Bioinformatics_ 2011,
**27**(6)**:**764-770. [Link](http://bioinformatics.oxfordjournals.org/content
/early/2011/01/07/bioinformatics.btr011)

Melsted P, Pritchard JK (2011) **Efficient counting of k-mers in DNA sequences
using a bloom filter. **_Bmc Bioinformatics_**12\.
****[Link](http://www.biomedcentral.com/1471-2105/12/333/)**

**C. T. Brown**** khmer ****<https://github.com/ctb/>**

**Storage**

Christley S, Lu Y, Li C, Xie X (2009) **Human genomes as email attachments.
Bioinformatics** ;25:274-275.

Conway TC, Bromage AJ (2011) ****Succinct data structures for assembling large
genomes. ****_Bioinformatics_**27**(4)**:**479-486. [Link](http://Link/)

Fritz MH-Y, Leinonen R, Cochrane G, Birney E. (2011) **Efficient storage of
high throughput DNA sequencing data using reference-based compression.
**Genome Res.;21:734-740.

Roberts M, Hayes W, Hunt BR, Mount SM, Yorke JA (2004) **Reducing storage
requirements for biological sequence comparison.
**_Bioinformatics_**20**(18)**:**3363-3369. [Link](http://Link/)

Pinho A, Pratas D, Garcia S (2012) **GReEn: a tool for efficient compression
of genome resequencing data.** Nucleic Acids Res 40: e27.
[Link](http://nar.oxfordjournals.org/content/early/2011/12/01/nar.gkr1124)

Daniel C. Jones, W. L. Ruzzo, X. Peng, M. G. Katze (2012) **Compression of
next-generation sequencing reads aided by highly efficient de novo assembly,
Nucleic Acids Research, **[Link](http://nar.oxfordjournals.org/content/early/2
012/08/14/nar.gks754.long) <https://github.com/dcjones/quip#readme>

Rayan Chikhiand Guillaume Rizk (2012) **Space-efficient and exact de Bruijn
graph representation based on a Bloom Filter. **[Link](http://Link/)

Kozanitis C, Saunders C, Kruglyak S, Bafna V, Varghese G. (2011) **Compressing
genomic sequence fragments using SlimGene**. _J Comput Biol._ (3):401-13.[Link
](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3123913/?tool=pubmed)

**Pell J. **_et al._(2012)** Scaling metagenome sequence assembly with probabilistic de Bruijn graphs, **_Proc. Nat. Acad. Sci. USA. _[Link](http://Link/)

C. Titus Brown, Adina Howe, Qingpeng Zhang, Alexis B. Pyrkosz, Timothy H. Brom
**A Reference-Free Algorithm for Computational Normalization of Shotgun
Sequencing Data <http://arxiv.org/abs/1203.4802>**

**Error correction**

Kelley D, Schatz M, Salzberg S: (2010) **Quake: quality-aware detection and
correction of sequencing errors. **_Genome Biology_**11**(11)**:**R116.

Medvedev P, Scott E, Kakaradov B, Pevzner P (2011) **Error correction of high-
throughput sequencing datasets with non-uniform coverage.** Bioinformatics 27:
i137-41.

C. Titus Brown, Adina Howe, Qingpeng Zhang, Alexis B. Pyrkosz, Timothy H. Brom
**A Reference-Free Algorithm for Computational Normalization of Shotgun
Sequencing Data <http://arxiv.org/abs/1203.4802>**

**Hadoop**

Schatz M (2009) **Cloudburst: highly sensitive read mapping with mapreduce.**
Bioinformatics 25: 1363-9.

Contrail <http://sourceforge.net/apps/mediawiki/contrail-
bio/index.php?title=Contrail>

**Hardware-accelerators**

Shi H, Schmidt B, Liu W, Mller-Wittig W (2010) **A Parallel Algorithm for
Error Correction in High-Throughput Short-Read Data on CUDA-Enabled Graphics
Hardware. **_Journal of Computational Biology_**17**(4)**:**603-615.

Liu Y, Schmidt B, Maskell DL (2011) **Parallelized short read assembly of
large genomes using de Bruijn graphs.** BMC Bioinformatics, 12:354.
[Link](http://Link/)

**String graph assembler**

Myers EW (2005) **The fragment assembly string graph.
**_Bioinformatics_**21:**79-85. [Link](http://bioinformatics.oxfordjournals.or
g/content/21/suppl_2/ii79.abstract)

Simpson JT, Durbin R: **Efficient de novo assembly of large genomes using
compressed data structures. **_Genome Res_ 2011\.
[Link](http://genome.cshlp.org/content/early/2011/12/07/gr.126953.111)

Simpson J, Durbin R (2010) **Efficient construction of an assembly string
graph using the fm-index.**

Bioinformatics 26: i367-73.
[Link](http://bioinformatics.oxfordjournals.org/content/26/12/i367.abstract)

Simpson J, Durbin R (2012) **Efficient de novo assembly of large genomes using
compressed data structures.** Genome Res 22: 549-56.
[Link](http://genome.cshlp.org/content/early/2011/12/07/gr.126953.111)

**Scaffolding**

Zerbino DR, McEwen GK, Margulies EH, Birney E (2009) **Pebble and rock band:
heuristic resolution of repeats and scaffolding in the velvet short-read de
novo assembler.** PLoS One 4: e8407.
[Link](http://www.plosone.org/article/info:doi/10.1371/journal.pone.0008407)

Koren S, Treangen T, Pop M (2011) **Bambus 2: scaffolding
metagenomes.**_Bioinformatics_ 27: 2964-71.
[Link](http://www.ncbi.nlm.nih.gov/pubmed/21926123)

Alexey A. Gritsenko _et al._ (2012) **GRASS: a generic algorithm for
scaffolding next-generation sequencing assemblies** Bioinformatics 28(11):
1429-1437 [Abstract](http://bioinformatics.oxfordjournals.org/cgi/content/abst
ract/28/11/1429)

**Repeats**

Zerbino DR, McEwen GK, Margulies EH, Birney E (2009) **Pebble and rock band:
heuristic resolution of repeats and scaffolding in the velvet short-read de
novo assembler.** PLoS One 4: e8407. [Link](http://Link/)

Do H, Choi K, Preparata F, Sung W, Zhang L (2008) **Spectrum-based de novo
repeat detection in genomic sequences.** _J Comput Biol_ 15: 469-87.
[Link](http://www.ncbi.nlm.nih.gov/pubmed/18549302)

Novak P, Neumann P, Macas J (2010) **Graph-based clustering and
characterization of repetitive sequences in next-generation sequencing data.**
_BMC Bioinformatics_ 11: 378.
[Link](http://www.biomedcentral.com/1471-2105/11/378)

Gu W, Castoe T, Hedges D, Batzer M, Pollock D (2008) **Identification of
repeat structure in large genomes using repeat probability clouds. **_Anal
Biochem_** 380: 77-83.
**[Link](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2533575/?tool=pubmed)

**6\. Reviews, visions and IMs**

Metzker M (2010) **Sequencing technologies - the next generation.**_Nat Rev
Genet_ 11: 31-46. [Link](http://www.ncbi.nlm.nih.gov/pubmed/19997069)

Shendure J. and Ji H. (2008) **Next-generation DNA sequencing**, _Nature
Biotechnol._ 26, 1135 1145.
[Link](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC317871/)

Phillippy AM, Schatz MC, Pop M (2008) ****Genome assembly forensics: finding
the elusive mis-assembly.********_Genome Biol_**9**(3)**.
[Link](http://genomebiology.com/content/9/3/R55)**

Miller J, Koren S, Sutton G (2010) **Assembly algorithms for next-generation
sequencing data.**_Genomics_ 95: 315-27.
[Link](http://www.ncbi.nlm.nih.gov/pmc/articles/PMC2874646/?tool=pubmed)

Trapnell C, Salzberg S (2009) **How to map billions of short reads onto
genomes.**_Nat Biotechnol_ 27: 455-7.
[Link](http://www.nature.com/nbt/journal/v27/n5/abs/nbt0509-455.html)

Stein L. (2010) **The case for cloud computing in genome informatics.**_Genome
Biol_ 11: 207. [Link](http://genomebiology.com/2010/11/5/207)

Li Y, Hu Y, Bolund L, Wang J (2010) **State of the art de novo assembly of
human genomes from massively parallel sequencing data.**_Hum Genomics_ 4:
271-7. [Link](http://www.ncbi.nlm.nih.gov/pubmed/20511140)

Compeau P, Pevzner P, Tesler G (2011) **How to apply de bruijn graphs to
genome assembly.**_Nat Biotechnol._ 29: 987-91.
[Link](http://www.nature.com/nbt/journal/v29/n11/full/nbt.2023.html)

Nagarajan N, Pop M (2009) **Parametric complexity of sequence assembly: theory
and applications to next generation sequencing.**_J Comput Biol _16: 897-908.
[Link](http://www.ncbi.nlm.nih.gov/pubmed/19580519)

**Carl Kingsford**, **Michael C Schatz** and **Mihai Pop** (2010) **Assembly Complexity of prokaryotic genomes using short reads **_BMC Bioinformatics_ 2010, **11**:21 [Link](http://www.biomedcentral.com/1471-2105/11/21/)

Pop M, Salzberg SL (2008) **Bioinformatics challenges of new sequencing
technology.** Trends Genet 24: 142149. [Link](http://Link/)

Flicek P, Birney E (2009) Sense from sequence reads: methods for alignment and
assembly. Nat Methods 6: S6S12. [Link](http://Link/) (pdf),
[Link](http://Link/)

