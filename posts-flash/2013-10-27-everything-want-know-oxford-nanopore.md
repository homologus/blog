---
title: Everything You Want to Know about Oxford Nanopore
tags: []
categories:
- blog
---
Over the last week, science blogs described the sequencing instrument of
Oxford Nanopore as everything from [hi-tech washing
machine](http://flxlexblog.wordpress.com/2013/10/25/would-you-buy-that-
washing-machine/) to [Nigerian scam, ZX-81 and Turbo Pascal combined
together](http://omicsomics.blogspot.com/2013/10/spanish-prisoner-zx-81-or-
turbo-pascal.html). We emailed the CEO of this supposedly ultra-secretive
company with those blog posts, and to our utter surprise, received a long
email reply describing everything they accomplished over the last two years.
<!--more-->

Well, we made up the last part in the above paragraph. No email exchange took
place with their company (editing to clarify this point), but we learned a lot
about their technologies. How so? Because unlike the public impression we get
about them as being highly secretive, the company is actually very open and
regularly posts many details about their technology online. From those
postings, a knowledgeable person should be able to put together quite a bit
about what they are up to and what their likely bottlenecks are. You do not
need a password to access that site and simply click on the links below. The
figures are not available from the linked website, but they can be easily
found online without help from NSA.

1\. [Hairpin loop method for double strand polynucleotide sequencing using
transmembrane pores](http://www.google.com/patents/WO2013014451A1?cl=en)

>

**Summary of the Invention**

The inventors have surprisingly demonstrated that both strands of a double
stranded target polynucleotide can be sequenced by a nanopore when the two
strands are linked by a bridging moiety and then separated. Furthermore, the
inventors have also surprisingly shown that an enzyme, such as Phi29 DNA
polymerase, is capable of separating the two strands of a double stranded
polynucleotide, such as DNA, linked by a bridging moiety and controlling the
movement of the resulting single stranded polynucleotide through the
transmembrane pore.

The ability to sequence both strands of a double stranded polynucleotide by
linking the two strands with a bridging moiety has a number of advantages, not
least that both the sense and anti-sense strands of the polynucleotide can be
sequenced. These advantages are discussed in more detail below.

Accordingly, the invention provides a method of sequencing a double stranded
target polynucleotide, comprising:

(a) providing a construct comprising the target polynucleotide, wherein the
two strands of the target polynucleotide are linked at or near one end of the
target polynucleotide by a bridging moiety;

(b) separating the two strands of the target polynucleotide to provide a
single stranded polynucleotide comprising one strand of the target
polynucleotide linked to the other strand of the target polynucleotide by the
bridging moiety;

(c) moving the single stranded polynucleotide through a transmembrane pore
such that a proportion of the nucleotides in the single stranded
polynucleotide interact with the pore; and

(d) measuring the current passing through the pore during each interaction and
thereby determining or estimating the sequence of the target polynucleotide,
wherein the separating in step (b) comprises contacting the construct with a

polynucleotide binding protein which separates the two strands of the target

polynucleotide.

The invention also provides:

a kit for preparing a double stranded target polynucleotide for sequencing
comprising (a) a bridging moiety capable of linking the two strands of the
target polynucleotide at or near one end and (b) at least one polymer;

a method of preparing a double stranded target polynucleotide for sequencing,
comprising:

(a) linking the two strands of the target polynucleotide at or near one end
with a bridging moiety; and

(b) attaching one polymer to one strand at the other end of the target
polynucleotide and thereby forming a construct that allows the target
polynucleotide to be sequenced using a transmembrane pore;

a method of sequencing a double stranded target polynucleotide, comprising:

(a) providing a construct comprising the target polynucleotide, wherein the
two strands of the target polynucleotide are linked at or near one end of the
target polynucleotide by a bridging moiety; (b) separating the two strands of
the target polynucleotide to provide a single stranded polynucleotide
comprising one strand of the target polynucleotide linked to the other strand
of the target polynucleotide by the bridging moiety;

(c) synthesising a complement of the single stranded polynucleotide, such that
the single stranded polynucleotide and complement form a double stranded

polynucleotide;

(d) linking the two strands of the double stranded polynucleotide at or near
one end of the double stranded polynucleotide using a bridging moiety;

(e) separating the two strands of the double stranded polynucleotide to
provide a further single stranded polynucleotide comprising the original
single stranded polynucleotide linked to the complement by the bridging
moiety;

(f) moving the complement through a transmembrane pore such that a proportion
of the nucleotides in the complement interact with the pore; and

(g) measuring the current passing through the pore during each interaction and
thereby determining or estimating the sequence of the target polynucleotide,
wherein the separating in step (e) comprises contacting the construct with a
polynucleotide binding protein which separates the two strands of the target
polynucleotide;

an apparatus for sequencing a double stranded target polynucleotide,
comprising: (a) a membrane; (b) a plurality of transmembrane pores in the
membrane; (c) a plurality of polynucleotide binding proteins which are capable
of separating the two strands of the target polynucleotide; and (d)
instructions for carrying out the method of the invention; and

an apparatus for sequencing a double stranded target polynucleotide,
comprising: (a) a membrane; (b) a plurality of transmembrane pores in the
membrane; and (c) a plurality of polynucleotide binding proteins which are
capable of separating the two strands of the target polynucleotide, wherein
the apparatus is set up to carry out the method of the invention.. Description
of the Figures

Fig. 1 shows a schematic of enzyme controlled dsDNA and ssDNA translocation
through a nanopore. An enzyme (e.g. Phi29 DNA polymerase) that is incubated
with dsDNA having an ssDNA leader binds at the ssDNA-dsDNA interface. DNA-
enzyme complexes are captured by a nanopore under an applied field. Under the
field, the template strand of the DNA is slowly stripped through the enzyme in
a controlled base-by-base manner, in the process unzipping the complementary
primer strand of the dsDNA in or above the enzyme. Once the enzyme reaches the
end of the dsDNA it falls off the D A, releasing it through the nanopore.

Fig. 2 shows another schematic of enzyme controlled dsDNA and ssDNA
translocation through a nanopore. The dsDNA has a hairpin turn linking the
sense and anti-sense strands of the dsDNA. Once the enzyme reaches the hairpin
it remains bound to the DNA, proceeds around the hairpin turn, and along the
anti-sense strand. In the hairpin and antisense regions the enzyme functions
as an ssDNA molecular brake, continuing to sufficiently control translocation
of the DNA through the nanopore to sequence the DNA.

Fig. 3 shows a schematic overview of reading around a hairpin of dsDNA using
the ability of the enzyme to control movement in ssDNA regions. The dsDNA has
a 5'-ssDNA leader to allow capture by the nanopore. This is followed by a
dsDNA section, where the sense and anti-sense strands are connected by a
hairpin. The hairpin can optionally contain markers (e.g. abasic residues,
shown in Fig. 3 as a cross) that are observed during sequencing, which permit
simple identification of the sense and anti-sense strands during sequencing.
The 3 '-end of the anti-sense strand can optionally also have a 3'-ssDNA
overhang, which if greater than ~20 bases allows full reading of the anti-
sense strand (the read-head of the nanopore is -20 bases downstrand from the
top of the DNA in the enzyme).

Fig. 4 shows a schematic of the DNA-Enzyme-nanopore complex (left) sequenced
in unzipping mode through MspA nanopores using Phi29 DNA polymerase, and the
consensus sequence obtained from them (right). Section 1 marks the sense
section of DNA, and section 2 marks the anti-sense section. This figure shows
DNA sequencing of a short dsDNA construct. In this construct the dsDNA section
is not connected by a hairpin, so the enzyme falls off the end of the DNA, and
only the template/sense strand is sequenced (except for the last -20 bases).

Fig. 5 shows a schematic of the DNA-Enzyme-nanopore complex (left) sequenced
in unzipping mode through MspA nanopores using Phi29 DNA polymerase, and the
consensus sequence obtained from them (right). Section 1 marks the sense
section of DNA, and section 2 the anti-sense section. DNA sequencing of a
short dsDNA construct with a hairpin. In this construct the enzyme moves along
the sense strand, around the hairpin loop, and down the anti- sense strand,
permitting sequencing of both the sense and the first part of the anti-sense
strand.

Fig. 6 shows a schematic of the DNA-Enzyme-nanopore complex (left) sequenced
in unzipping mode through MspA nanopores using Phi29 DNA polymerase, and the
consensus sequence obtained from them (right). Section 1 marks the sense
section of DNA, and section 2 the anti-sense section. Similar to Fig. 5, this
construct permits sequencing of both the sense and anti-sense strands, but the
additional 3'-ssDNA overhang permits reading of the full length of the anti-
sense strand before the enzyme falls off the end of the DNA. Fig. 7 shows a
schematic of the DNA-Enzyme-nanopore complex (left) sequenced in unzipping
mode through MspA nanopores using Phi29 DNA polymerase, and the consensus
sequence obtained from them (right). Section 1 marks the sense section of DNA,
and section 2 the anti-sense section. Similar to Fig. 5, this construct
permits sequencing of both the sense and anti-sense strands, however, this
construct has a single abasic residue (shown as a cross) in the hairpin, which
provides a clear marker in the DNA sequence to identify the sense and anti-
sense sections.

Fig. 8 shows the consensus DNA sequence of UA02 through MspA. Section 1 marks
the homopolymeric 5 '-overhang initially in the nanopore. Section 2 marks the
sense section of the DNA strand. Section 3 marks the turn. Section 4 marks the
anti-sense region of the DNA strand. The polynucleotide sequence that
corresponds to each section is shown below that section number.

Fig. 9 shows a schematic of a genomic template for unzipping through MspA
nanopores using Phi29 DNA polymerase. It shows a general design outline for
creating dsDNA suitable for reading around hairpins. The constructs have a
leader sequence with optional marker (e.g. abasic DNA) for capture in the
nanopore, and hairpin with optional marker, and a tail for extended reading
into anti-sense strand with optional marker.

Fig. 10 shows a schematic of the adapter design for ligating ssDNA overhangs
(left) and hairpin turns (right) onto genomic dsDNA. X = abasic DNA. Choi =
cholesterol-TEG DNA modification.

Fig. 11 shows typical polymerase controlled DNA movement of a 400mer-hairpin
through MspA using Phi29 DNA polymerase. Sense region = abasic 1 to 2. Anti-
sense region = abasic 2 to 3.

Fig. 12 shows a consensus DNA sequence profile from multiple polymerase
controlled DNA movements of a 400mer-hairpin through MspA. Sense region =
abasic 1 to 2. Anti-sense region = abasic 2 to 3.

Fig. 13 shows a schematic of an alternative sample preparation for sequencing.
A construct is illustrated comprising the target polynucleotide and a bridging
moiety (hairpin) linking the two strands of the target polynucleotide. The
construct also comprises a leader polymer (a single stranded sequence), a tail
polymer (also a single stranded sequence) and an abasic marker region within
the leader. The marker may prevent the enzyme from making the template
completely blunt ended i.e. filling in opposite the required leader ssDNA. A
strand displacing polymerase (nucleic acid binding protein) separates the two
strands of the construct, initiating either via a complementary primer or by
protein primed amplification from the tail polymer. A complement is generated
to the resulting single stranded polynucleotide. The complement and the
original sense and antisense single stranded polynucleotide analyte can be
further modified by addition of a second bridging moiety (hairpin).

Fig. 14 shows a specific preparation of the construct comprising the target

polynucleotide.

Fig. 15 shows where amplification may be added as part of the sample
preparation to aid the detection of epigenetic information. A nucleotide has
been constructed so that the following information is read through the pore:
sense (original), antisense (original), bridging moiety, sense (replicate),
antisense (replicate). Information on the methylated base (mC) is therefore
obtained four times.

Fig. 16 shows how RNA can be sequenced. A bridging moiety is attached to a
piece of

R A and the DNA reverse complement added to the RNA via a reverse
transcriptase. The RNA is read, followed by the DNA of the reverse complement.

Fig. 17 shows a schematic of helicase controlled dsDNA and ssDNA translocation
through a nanopore. The dsDNA has a hairpin turn linking the sense and anti-
sense strands of the dsDNA. Once the enzyme reaches the hairpin it remains
bound to the DNA, proceeds around the hairpin turn, and along the anti-sense
strand. In the hairpin and antisense regions the enzyme functions as an ssDNA
molecular brake, continuing to sufficiently control translocation of the DNA
through the nanopore to sequence the DNA.

Fig. 18 shows the polynucleotide MONO hairpin construct (SEQ ID NOs: 29 to 35)
used in Example 4.

Fig. 19 shows a typical helicase controlled DNA movement of a 400 bp hairpin
(SEQ ID NOs: 29 to 35 connected as shown in Fig. 18) through an MspA nanopore
(MS(B1-G75S-G77S- L88N-Q126R)8 MspA (SEQ ID NO: 2 with the mutations
G75S/G77S/L88N/Q126R)). Sense = region 1. Anti-sense = region 2.

Fig. 20 shows the beginning of a typical helicase controlled DNA movement of a
400 bp hairpin (SEQ ID NOs: 29 to 35 connected as shown in Fig. 18) through an
MspA nanopore (MS(B1-G75S-G77S-L88N-Q126R)8 MspA (SEQ ID NO: 2 with the
mutations

G75S/G77S/L88N/Q126R)). The polyT region at the beginning of the sequence is
highlighted with a * and the abasic DNA bases as a #.

Fig. 21 shows the transition between the sense and antisense regions of a
typical helicase controlled DNA movement of a 400 bp-hairpin (SEQ ID NOs: 29
to 35 connected as shown in Fig. 18) through an MspA nanopore (MS(B1-G75S-
G77S-L88N-Q126R)8 MspA (SEQ ID NO: 2 with the mutations
G75S/G77S/L88N/Q126R)). The transition region between the sense and antisense
regions of the sequence is highlighted by a * , the sense region labeled 1 and
the antisense region labeled 2. Fig. 22 shows an example sample prep method
for forming DUO hairpin constructs. The double stranded DNA analyte is
contacted by and modified to contain a Y-shaped adapter (the sense strand (SEQ
ID NO: 29 attached to SEQ ID NO: 30 via four abasic DNA bases) of this adaptor
contains the 5' leader, a sequence that is complementary to the tether (SEQ ID
NO: 35, which at the 3' end of the sequence has six iSpl 8 spacers attached to
two thymine residues and a 3' cholesterol TEG) and 4 abasics and the antisense
half of the adaptor contains a 3' hairpin (SEQ ID NO: 31)) at one end of the
duplex and a hairpin (SEQ ID NO: 32) at the other. The Y- shaped adapter
itself also carries a 3 '-hairpin (SEQ ID NO: 31), which allows extension
either by a polymerase or by ligation. This extension is preferentially
carried out by a mesophilic polymerase that has strand displacement activity.
As the polymerase extends from the 3 ' of the Y-shaped adapter hairpin (SEQ ID
NO: 31) it copies the antisense strand (SEQ ID NO: 34) and so displaces the
original sense strand (SEQ ID NO: 33). When the polymerase reaches the end of
the antisense strand (SEQ ID NO: 34) it fills-in opposite the hairpin (SEQ ID
NO: 32) and then begins to fill-in opposite the now single stranded and
original sense strand (SEQ ID NO: 33). Extension is then halted by a section
of abasic or spacer modifications (other possible modifications which could
halt enzyme extension include RNA, PNA or morpholino bases and iso-dC or iso-
dG) to leave the 5 '-region of the Y-shaped adapter single stranded (SEQ ID
NO: 29).

Fig. 23 shows the specific preparation method used in Example 5 for preparing
a DUO hairpin construct (SEQ ID NOs: 29 to 36 connected as shown in Fig. 25).
A -400 bp region of PhiX 174 was PCR amplified with primers containing Sad and
Kpnl restriction sites (SEQ ID Nos: 27 and 28 respectively). Purified PCR
product was then Sad and Kpnl digested before aY- shaped adapter (sense strand
sequence (SEQ ID NO: 29 attached to SEQ ID NO: 30 via four abasic DNA bases)
is ligated onto the 5' end of SEQ ID NO: 33 and the anti-sense strand (SEQ ID
NO: 31) is ligated onto the 3 ' end of the SEQ ID NO: 34) and a hairpin (SEQ
ID NO: 32, used to join SEQ ID NO's: 33 and 34) were ligated to either end,
using T4 DNA ligase (See Fig. 18 for final DNA construct). The doubly ligated
product was PAGE purified before addition of lenow DNA polymerase, SSB and
nucleotides to allow extension from the Y-shaped adapter hairpin (SEQ ID NO:
31). To screen for successful DUO product a series of mismatch restriction
sites were incorporated into the adapter sequences, whereby the enzyme will
cut the analyte only if the restriction site has been successfully replicated
by the DUO extension process.

Fig. 24 shows that the adapter modified analyte (MONO, SEQ ID NOs: 29-35
connected as shown in Fog. 18) in the absence of polymerase does not digest
with the restriction enzymes (see gel on the left, Key: M = Mfel, A = Agel, X
= Xmal, N = NgoMIV, B = BspEl), due to the fact they are mismatched to one
another. However, on incubation with polymerase there is a noticeable size
shift and the shifted product (DUO, SEQ ID NOs: 29-36 connected as shown in
Fig. 25) now digests as expected with each of the restriction enzymes (see gel
on the right, Key: M = Mfel, A = Agel, X = Xma\, N = NgoMIV, B = BspEl).

Fig. 25 shows the polynucleotide DUO hairpin construct (SEQ ID NOs: 29 to 36)
used in Examples 6.

Fig. 26 shows two typical helicase controlled DNA movements for the DUO
hairpin construct (SEQ ID NOs: 29 to 36 connected as shown in Fig. 25) through
an MspA nanopore (MS(B1-G75S-G77S-L88N-Q126R)8 MspA (SEQ ID NO: 2 with the
mutations

G75S/G77S/L88N/Q126R)). Sense original = region 1. Anti-sense original =
region 2. Sense replicate = region 3. Anti-sense replicate = region 4.

Fig. 27 shows an expanded view of a typical helicase controlled DNA movement
for the DUO hairpin construct (SEQ ID NOs: 29 to 36 connected as shown in Fig.
25) through an MspA nanopore (MS(B1-G75S-G77S-L88N-Q126R)8 MspA (SEQ ID NO: 2
with the mutations G75S/G77S/L88N/Q126R)). Sense original = region 1. Anti-
sense original = region 2. Sense replicate = region 3. Anti-sense replicate =
region 4.

Fig. 28 shows an expanded view of a typical transition between the sense
original and antisense original regions of the DUO hairpin construct (SEQ ID
NOs: 29 to 36 connected as shown in Fig. 25) when under helicase controlled
DNA movement through an MspA nanopore (MS(B1-G75S-G77S-L88N-Q126R)8 MspA (SEQ
ID NO: 2 with the mutations.

2\. [Apparatus for supporting an array of layers of amphiphilic molecules and
method of forming an array of layers of amphiphilic
molecules](http://www.google.com/patents/WO2013121193A2?cl=en)

> An apparatus for supporting an array of layers of amphiphilic molecules, the
apparatus comprising: a body,formed in a surface of the body, an array of
sensor wells capable of supporting a layer of amphiphilic molecules across the
sensor wells, the sensor wells each containing an electrode for connection to
an electrical circuit, and formed in the surface of the body between the
sensor wells, flow control wells capable of smoothing the flow of a fluid
across the surface.

3\. [Aptamer method](http://www.google.com/patents/WO2013121201A1?cl=en)

The invention relates to a new method of determining in a sample the presence
or absence of one or more analyte members of a group of two or more analytes.
The invention therefore relates to a multiplex assay for determining the
presence or absence of each analyte in a group of multiple analytes. The assay
uses aptamers and transmembrane pores.

4\. [Analysis of measurements of a
polymer](http://www.google.com/patents/WO2013121224A1?cl=en)

> A time-ordered series of measurements of a polymer made during translocation
of the polymer through a nanopore are analysed. The measurements are dependent
on the identity of k-mers in the nanopore, a k-mer being k polymer units of
the polymer, where k is a positive integer. The method involves deriving, from
the series of measurements, a feature vector of time-ordered features
representing characteristics of the measurements; and determining similarity
between the derived feature vector and at least one other feature vector.

5\. [Method for characterising a polynucelotide by using a xpd
helicase](http://www.google.com/patents/WO2013098561A1?cl=en)

> The invention relates to a new method of characterising a target
polynucleotide. The method uses a pore and an XPD helicase. The helicase
controls the movement of the target polynucleotide through the pore.

6\. [Enzyme method](http://www.google.com/patents/WO2013057495A2?cl=en)

> The invention relates to a new method of characterising a target
polynucleotide. The method uses a pore and a Hel308 helicase or amolecular
motor which is capable of binding to the target polynucleotide at an internal
nucleotide. The helicase or molecular motor controls the movement of the
target polynucleotide through the pore.

7\. [Analysis of a polymer comprising polymer
units](http://www.google.com/patents/WO2013041878A1?cl=en)

> A sequence of polymer units in a polymer (3), eg. DNA, is estimated from at
least one series of measurements related to the polymer, eg. ion current as a
function of translocation through a nanopore (1), wherein the value of each
measurement is dependent on a k-mer being a group of k polymer units (4). A
probabilistic model, especially a hidden Markov model (HMM), is provided,
comprising, for a set of possible k-mers: transition weightings representing
the chances of transitions from origin k-mers to destination k-mers; and
emission weightings in respect of each k-mer that represent the chances of
observing given values of measurements for that k-mer. The series of
measurements is analysed using an analytical technique, eg. Viterbi decoding,
that refers to the model and estimates at least one estimated sequence of
polymer units in the polymer based on the likelihood predicted by the model of
the series of measurements being produced by sequences of polymer units. In a
further embodiment, different voltages are applied across the nanopore during
translocation in order to improve the resolution of polymer units.

8\. [Piston seal](http://www.google.com/patents/WO2013038164A2?cl=en)

> A piston head for a syringe pump comprises a barrier portion for driving
fluid through a syringe pump barrel, wherein a peripheral section of the
barrier portion is shaped to seal against the syringe pump barrel; and a
resilient member arranged to resist deformation of the shaped peripheral
section of the barrier portion.

How about data? We have not seen any nucleotide-level data yet, but the first
patent mentioned above contains many figures showing their electrical signals.
One informative comment at OmicsOmics blog speculated on what could be going
on at the company.

> Interesting discussion here. I too went ahead and glanced through OxNano's
patent applications. Based on my very quick review, here is what I found

1\. They have done extensive amount of work on mspA, but Illumina licenced the
pore now. Not sure what is going on there

2\. The closest I saw anything related to sequencing was a bioinformatics
patent application that describes how to convert K mer signatures to sequence
- there was't any sequencing data in that application

3\. They seem to have some cool motors. Helicases from some extremophiles

4\. One new pore called lysenin, not sure how it compares to mspA. No
sequencing information in the patent application

5\. Some algorithms to build consensus among traces (squiggles, if that is the
terminology we are using)

6\. There was one application where the did some algorithmic learning on a
known piece of DNA, I didn't see that extended to an unknown sample

Regarding the comment that investors probably saw sequencing data, that could
be true. Wonder if that caused the rift with Illumina. They clearly convinced
Illumina with a sequencing scheme, now they have convinced other investors of
a different scheme. Time to convince the users.

Our views are in line with another comment -

> The squiggles have been around for quite some time now. Both the Akeson and
Gundlach labs have published the squiggles. Credit to Oxford for putting
things in a nice package, but unless I see them convert the squiggles to
sequence, I, sadly, will have to assume they are being evasive and just trying
to buy time.

...

This other thought, I keep having because I hear how secretive and paranoid
Oxford are. I am beginning to wonder if it is just a rouse to hide serious
deficiencies they are trying, or unable to fix (with lots of investors and the
world looking at them).

Buy time is what it is.

