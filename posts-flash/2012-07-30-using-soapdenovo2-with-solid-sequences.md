---
title: Using SOAPdenovo2 with SOLiD Sequences
tags: []
categories:
- blog
---
Earlier, we reported about BGI's plans to release a new version of the popular
SOAPdenovo2 software. We received a pre-release copy and tested it on one of
our unpublished libraries (mentioned
[here](http://www.homolog.us/blogs/2012/06/27/testing-soapdenovo2/),
[here](http://www.homolog.us/blogs/2012/07/04/testing-soapdenovo2-pre-release-
version-part-ii/), [here](http://www.homolog.us/blogs/2012/07/05/testing-
soapdenovo2-prelease-version-iii/) and
[here](http://www.homolog.us/blogs/2012/07/05/testing-soapdenovo2-prerelease-
iv-building-contigs/)). The final report from that comparison is still
pending, and will be posted as soon as we can catch a breath from other work.
<!--more-->

BGI invested heavily on Illumina machines, and therefore their software tools
are best tuned to handle Illumina libraries. However, researchers with other
types of data should not lose hope. Those working on SOLiD data may find [this
email exchange](https://mail.google.com/mail/h/11r6k947rs3hf/?&v=c&s=q&q=solid
&th=1387c53259f60744) in SOAPdenovo mailing list helpful.

Here was our suggestion in the above exchange:

> The best way to proceed would be to

i) correct color space mate pair reads using contigs assembled by SOAPdenovo,

ii) translate corrected color space to nucleotide space,

iii) treat translated mate pair library like a Illumina mate pair library.

....

How to do (i) listed above?

(a) Run 'SOAPdenovo pregraph' and 'SOAPdenovo contig' to assemble

contigs from Illumina reads.

(b) Translate contigs to color space (pseudonucleotide) and use Bowtie

to map color space reads,

(c) Based on above mapping, correct as many color space reads as possible.

Let us add few sentences on why we proposed the above procedure.

The readers may note that the researcher asking question had his paired end
reads in Illumina format. Only his longer mate pairs are in SOLiD format.

One difficulty of SOLiD reads is that if they are translated directly from
color space to nucleotide space, [translation becomes completely
meaningless](http://www.homolog.us/blogs/2010/02/15/the-mathematics-behind-
color-space-sequencing/) for reads containing single color space errors.
However, having Illumina reads give the user an excellent opportunity to clean
up SOLiD reads before translating them. The clean-up procedure is less
cumbersome than cleaning PacBio reads, because the user can use the first two
steps of SOAPdenovo2 (preprocessing, building contigs) on the Illumina PE
libraries. Longer paired end libraries become important only for scaffolding,
which is a later stage of SOAPdenovo2 run.

So, the user can first assemble contigs from Illumina, then correct SOLiD
reads and finally proceed with nucleotide-space translation of corrected SOLiD
reads.

One point mentioned by Ruibang Luo is very important, while dealing with SOLiD
reads.

> Please aware that SOLiD uses FF orientation since Illumina uses FR in pair-
end reads and RF in mate pairs, when using soapdenovo for SOLiD, please
reverse complement right side reads and use reverse=0

Please go through [our earlier
commentary](http://www.homolog.us/blogs/2012/02/19/illumina-paired-end-
libraries-inward-and-outward-looking-reads/), if the above comment is not
clear.

What will an user do, if all his libraries in SOLiD format? The suggestion
from Kevin McKernan is the only hope in such a situation.

> Pavel Pevzner published work on kmer error correcting SOLiD reads.

Error correction is even better in color space as SNP look different than
errors. I don't know if the SOAP tools can do this but one trick we've used to
make other base space tools work on color space data is to perform a literal
transliteration of 0,1,2,3 -> A,T,C,G.

Perform the soap error correction and then translate back to 0,1,2,3.

Youll then have error corrected color space reads which you perform color to
base translations on which are immune to the frame shifting issues.

I think Pavels technique takes into consideration the adjacent errors as being
SNPs and it better tuned for this. I think Life Tech may have version of this
available.

