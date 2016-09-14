---
title: End of Short-Read Era? &ndash; (Part II)
tags: []
categories:
- blog
---
PacBio reads are long (~10 Kb) but noisy at the nucleotide level. In [part I
of this commentary](http://www.homolog.us/blogs/blog/2013/09/21/end-illumina-
era/), I argued that the short reads are also 'noisy' in a different way.
Their loss of information through short length manifests into producing lower
quality genomes and transcriptomes. Cleaning up of the noise at the genome and
transcriptome level adds to significant bioinformatics cost. Now that the
excitement of publishing 'draft' genomes of various cool plants and animals is
over, choice of short vs long technology will depend on the total cost for
acquiring different kinds of biological information. What is biologically
informative varies from project to project and it is not straightforward to
compare the cost of information content for two technologies. However, a
number of talks at the recent PacBio user group meeting mentioned that the
long PacBio reads are competitive at cost per information content, when users
are looking for fully assembled small to mid-sized genomes, or reconstructing
complex genomic regions (MHC) or isoforms from transcriptome.
<!--more-->

**Metagenome**

![](http://genome.wustl.edu/image/2/270/300/2/images/sections/individuals/wein
stock.jpg)

[George Weinstock](http://genome.wustl.edu/people/individual/george-
weinstock/) gave a nice talk on using PacBio in the human microbiome project.
The larger goals of the metagenomics field are somewhat blurry to me. [I asked
Titus Brown one year back](http://www.homolog.us/blogs/blog/2012/09/15/in-
turf-battle-for-computational-biology-ctb-fires-a-shot/comment-
page-1/#comment-17709), but did not get any answer.

![Capture](http://www.homolog.us/blogs/wp-
content/uploads/2013/09/Capture9-300x71.png)

The basic premise is clear (if one collects and sequences uncultured samples
from all places of earth, one will find unusual microbes), but at what cost is
that worth doing? The field started, when Craig Venter got NIH to pay for a
long sailing trip across the Atlantic. He collected, sequenced and compared
ocean samples from various places. Venter is a famous man and if he decided to
fish during the trip instead, he could have started the field of
'meta'-ichthyology.

Without understanding the larger goal, it is hard for me to say whether long
reads and full genomes (PacBio) are more informative in metagenomics or
whether the depth of sequencing (Illumina) is more relevant. Dr. Weinstock's
talk mentioned one medically important application - finding _C. dificile_ in
gut microbiome.

During lunch, I asked others about metagenomics and gut microbiome and learned
about a rather curious anecdote. Apparently, the disbalance of gut microbiome
can lead to serious illness, but an unique cure exists (check
[here](http://www.mayoclinic.org/medicalprofs/fecal-transplants-
ddue1012.html),
[here](http://www.omaha.com/article/20130513/LIVEWELL01/705139957/1685) and
[here](http://en.wikipedia.org/wiki/Fecal_bacteriotherapy)). Make sure you
finish your own lunch before checking the above links. As it appears, FDA
banned administering poop therapy and so the patients are resorting to doing
it on their own (not an enticing idea). Maybe metagenomic sequencing will be a
part of regulatory process, and what is being done for free by going through
instructions in wiki will be done in a hospital after paying for doctor,
sequencing and a robot doing the dirty work. (Edit. Keith Robison corrected us
on FDA status of fecal therapy - "fDA has not banned fecal transplants; has
decreed that they are an IND with consequent regulatory requirements").

Digression apart, other practical application of metagenomics I found so far
comes from a Boston-based company (Warp Drive Bio), [which sequences
metagenomes to find drugs from natural
products](http://www.homolog.us/blogs/blog/2013/09/03/metagenomics-expensive-
train-going-nowhere/). Based on public tweets of their leading
bioinformatician, the company likely uses PacBio sequencing in their genome
assembly pipeline to get complete microbial genomes.

**Business Aspects - A Thought Experiment**

I received a number of tweets and email messages on part I of this commentary,
and most of them highlighted the business aspects. Paraphrasing those comments
-

"Yes, PacBio reads are helpful, but the machines are too expensive compared to
PGM/MiSeq."

"Many people are waiting for long reads from nanopore sequencing."

"The company is unprofitable and will not survive."

"It is better to think about hybrid assembly than PacBio only."

Before going into the business aspects, let me do a 'thought experiment'.
Imagine the world were full of PacBio instruments today instead of short read
sequencers, and a HiSeq is introduced. Would the HiSeq and alike find any
market?

What would the PacBio-only world look like? Here is an imaginary description.
All core labs and sequencing centers transitioned nicely from Sanger reads to
10X longer PacBio reads in 2010. Acquiring genomes and transcriptomes is
fairly easy now and so is it to sort out two copies of diploid chromosomes. As
an example of solving medically relevant problems, biologists are using the
phasing information to figure out how recessive traits work in heterozygous
genotypes.

If a short read instrument is introduced into the above world, how would it
sell? I brought that up, because one drawback of PacBio mentioned by
BioMickWatson is [population level
statistics](http://biomickwatson.wordpress.com/2013/08/01/bacterial-genomes-
2nd-and-3rd-generation/).

> Population level statistics Im not sure of the fold coverage one achieves
with PacBio, but 40x Illumina coverage certainly lets you begin to see low-
level variants in the population of cells being sequenced.

I am not saying that the above is not a valid objection, but in a long-read
only world, the sellers of short-read technology would have had to work very
hard to convince everyone that the problem being solved had justifiable merit
compared to the costs of instrument and supporting infrastructure. Speaking of
supporting infrastructure, you need to take into account the high-RAM/high-
storage computers and vast network of talented scientists (Heng Li for
example) working hard to develop BWT-based nucleotide search algorithms. Many
of those programs would have had less chance to get developed in a PacBio-only
world, and the potential users of the short read data could have got stuck
with large amount of 'expensive-to-process' sequences. Taking those
difficulties into account, could a HiSeq be at all introduced in a PacBio-
saturated world? I am doubtful, because even the supposedly difficult problems
such as the one mentioned by BioMickWatson could be solved by adding more SMRT
cells. Expensive that may be, but much less than developing an entire
infrastructure of computers, storage systems and bioinformaticians for
processing short reads.

We live in a polar-opposite world, and I find it quite fascinating that PacBio
is able to make strong business case despite having little wind behind their
sails. Clearly the computational and mathematical challenges for solving many
biologically relevant problems (such as assembling MHC of orangutans from
short reads) is more expensive than sending samples to a PacBio core facility.
In some ways, I find that the current focus on connecting SNP-variants with
diseases or traits is related to the technological limitations of short-read
sequencing. With a different technology, the questions would have been asked
differently. Please correct me, if I am wrong.

Edit. Keith Robison disagrees....

![Capture-cancer](http://www.homolog.us/blogs/wp-content/uploads/2013/09
/Capture-cancer-300x131.png)

and Jason Chin offered an alternative.

![Capture2](http://www.homolog.us/blogs/wp-
content/uploads/2013/09/Capture22-300x84.png)

Nobody knows what would have happened. That is one problem of thought
experiment.

**Business Aspect - PacBio Finances**

Fantasies aside, let us take a look at the world as it exists today. After
listening to the talks at the user group meeting, I decided to go through the
[annual reports and financial statements of the
company](http://finance.yahoo.com/q/ks?s=PACB+Key+Statistics). Please note
that we are not professional financial analysts and have not blown up any bank
to add to our credentials. So, do your own due diligence (or [hire this
guy](http://www.businessweek.com/articles/2013-09-12/where-is-dick-fuld-now-
finding-lehman-brothers-last-ceo)) for financial decisions instead of relying
on what is said here.

PacBio spent ~$550M so far to develop their technology, which is comparable to
what ENCODE wasted and will continue to waste in the future with [blessings
from Eric Green of NIH](http://www.genome.gov/27535200). Despite the losses,
PacBio's model is far more productive and accountable to the society. When
Eric Green or Ewan Birney fail, they get promoted.

The company is [burning 80 million dollars every
year](http://finance.yahoo.com/q/is?s=PACB) at the latest quarterly run rate.
With 342 employees, that is $234K per employee. I compared the numbers to
JGI's, and Alex Copeland's talk was helpful in giving us the number. At $65
million/year and 250 employees, JGI's run rate is $260K/employee. Illumina,
[at $652 million for 2400 employees](http://finance.yahoo.com/q/is?s=ILMN), is
in the same ballpark - $272K/employee. You need to keep in mind that the
numbers include the costs of reagents, chemicals and instruments purchased by
the organizations, but those expenses are finally decided by the employees,
isn't it? What I took from the above back-of-the-envelop analysis is that
PacBio is not indulging on employee parties.

Further digging into the [financial statement](http://yahoo.brand.edgar-online
.com/displayfilinginfo.aspx?FilingID=9448434-8346-103928&type=sect&dcn=0001193
125-13-328986) revealed a partly troubling and partly hopeful situation.
PacBio managers received a loan from [an unethical Wall Street
company](http://www.sec.gov/litigation/admin/2013/34-70398.pdf), which seems
to specialize in shorting biotech companies under death spiral. Are they
preying on soon-to-be-dying PacBio?

That is no fault of the PacBio managers, but non-performance can lead to
headaches, whereas the 8.75% of interest rate (a notch below near-bankrupt
India) is nothing to write home about. The hopeful situation - the "Milestone"
of $41M of revenue by next year is a substantial gain from what it is today,
even though it will cover only half of $80M of expenses. How long will the
investors allow the company to burn cash?

> On February 5, 2013, we entered into a Facility Agreement (the Facility
Agreement) with entities affiliated with Deerfield Management Company, L.P.
(collectively, Deerfield), pursuant to which Deerfield agreed to provide $20.5
million in funding to us (the Facility). Under the terms of the Facility
Agreement, we issued to Deerfield promissory notes in the aggregate principal
amount of $20.5 million (the Notes). The Notes bear simple interest at a rate
of 8.75% per annum, payable quarterly in arrears commencing on April 1, 2013
and on the first business day of each January, April, July and October
thereafter. We received net proceeds of $20.0 million, representing $20.5
million of gross proceeds, less a $500,000 facility fee, before deducting
other expenses of the transaction.

The Facility Agreement has a maximum term of seven years from inception;
however it provides for the early repayment of principal in the event we have
net sales (as defined in the Facility Agreement) of less than $41.0 million
for the twelve-month period from the beginning of the second calendar quarter
of 2014 through the first calendar quarter of 2015 (the Milestone). If the
Milestone is not achieved, at Deerfields option, one-third of the original
principal balance of the Facility will become due, on each of the third,
fourth and fifth anniversaries of the date of the Facility Agreement.

From and after the date of the Facility Agreement, at the election of the
holders of Notes representing a majority of the aggregate principal amount of
the outstanding Notes, we shall apply 25% of the net proceeds from any
financing that includes an equity component, including without limitation, the
sale or issuance of our common stock, options, warrants or other securities
convertible or exchangeable for shares of our common stock, to the payment of
the Notes. This right is subject to certain exceptions set forth in the
Facility Agreement, including that the right will not apply until we have
issued 15.0 million shares (as adjusted for any stock split or reverse stock
split) of our common stock or rights to acquire our capital stock following
the date of the Facility Agreement.

Deerfield has the option to require us to repay the Notes if we complete a
Major Transaction (as defined in the Facility Agreement), including a change
of control or a sale of all or substantially all of our assets. Additionally,
the principal balance of the Facility may become immediately due and payable
upon an Event of Default (as defined in the Facility Agreement), in which case
Deerfield would have the right to require us to repay 100% of the principal
amount of the loan, plus any accrued and unpaid interest thereon. The Facility
Agreement does not provide for a prepayment of the Notes at our option.

The Facility Agreement also contains various representations and warranties,
and affirmative and negative covenants, customary for financings of this type,
including restrictions on the ability of the Company and its subsidiaries to
incur additional indebtedness or liens on its assets, except as permitted
under the Facility Agreement. In addition, we are required to maintain
consolidated cash and cash equivalents on the last day of each calendar
quarter of not less than $2.0 million. **As security for our repayment of our
obligations under the Facility Agreement, we granted to Deerfield a security
interest in substantially all of our property and interests in property.**

Overall I did not find any major surprise in their balance sheet.

**Business Aspect - What happens to strong technology of a bankrupt company?**

Many researchers assume that if the company goes bankrupt or runs out of
money, that will be the end of this wonderful long-read technology. That is
far from true. In 2000, a telecom business named Global Crossing went bankrupt
after building underwater fiber-optic cables to connect the continents. The
cables remained however, and other companies with cash purchased them at
discount prices to build global internet connectivity. I do not think the
technology will go away, unless being surpassed by better options from
competitors.

**Business Aspect - Competition**

That brings us to the other question. Will companies like Oxford Nanopore
develop long-read technologies to support the needs of the market and surpass
PacBio? I [wrote the first paper on how to compute electrical conductivity of
single organic molecule](http://chem-
faculty.ucsd.edu/kubiak/publications/79.pdf), long before the scientific field
got known as 'nanotechnology'. When [Agilent and Harvard announced nanopore
'breakthrough'](http://www.bioresearchonline.com/doc/agilent-harvard-to-
develop-breakthrough-techn-0002) in 2001, I was at NASA trying to build nano-
circuits. One bad effect of following a field for too long is seeing too much
BS and knowing where all dead bodies are buried. Why did [Illumina leave
Oxford Nanopore](http://www.genomeweb.com/sequencing/oxford-nanopore-illumina-
cut-ties) after buying Moleculo? Did they figure out that a bird in hand is
worth ten 'GridIONs' in bush?

I think the competition for PacBio is more likely to come from the established
companies and technologies. Companies like Illumina generate positive cash
flow, and can see and think about likely challenges to their existing business
model. BGI keeps pushing on trying to get longer mate pair junctions. The
group working on SPAdes assembler developed an algorithmic approach to
scaffold microbial genomes from small reads. So, all options for reducing
'noise' or loss of information from short reads possibly have not been
exhausted.

**Business Aspect - Views from a Core Facility**

Global economic downturn is one factor working in favor of and against PacBio.
Bobby Sebra of Mt. Sinai mentioned in his talk that the users were ok with
spending below $500/sample, but uncomfortable beyond that magic number. That
matches with my experience in various projects as well. Sequencing cost of
each SMRT cell is below that amount and that is a plus for PacBio.

The big minus, of course, is the cost of the instrument itself. At

$750K, it is comparable to HiSeq machine, but beyond the reach of individual
labs, who may afford a PGM or MiSeq. Four years back, US government was
distributing cash like candies to institutions to 'stimulate' the economy, but
now the most one can get from the government is a [guitar-playing appearance
of Francis Collins](http://www.youtube.com/watch?v=ob-r5MPa-ms).

Still, my contrarian view says that PGMs and MiSeqs are saturating the market.
That is exciting for bioinformaticians, but a core facility can distinguish
itself in a crowded arena by thinking differently. Several factors beyond
machine cost will affect that decision. Do employees cost $250K/person for
core facilities in USA, UK and continental Europe? What are the differences in
cost between sample preparation for two instruments? How comparable are the
machine throughputs? How expensive is bioinformatics? Is there an edge in the
kind of problems you can solve? One or two ants trying to be different starts
a new trend, and can eventually move an elephant.

That ends my naive and somewhat one-sided summary of the recent PacBio user
group meeting. Please feel free to ask any question or correct any error.

\-----------------------------------------------------------

Update. Sept 25

Today [PacBio announced exclusive deal with Roche on developing in vitro
diagnostics products](http://www.nasdaq.com/article/pacific-biosciences-to-
partner-with-roche-on-in-vitro-diagnostics-products-20130925-00564). That will
change a few things in the above commentary.

1\. PacBio will get $35M upfront and $40M after reaching certain milestones.
Those numbers are big and will impact the financial estimates and forecasts
mentioned above.

2\. Roche will be exclusive distributor for human in vitro diagnostics of
PacBio products.

> Roche will receive exclusive distribution rights for the products in the
area of human in vitro diagnostics, while Pacific Biosciences will continue to
market its current and future products for all fields outside that space,
including research, plant, animal and applied markets.

That is both good and bad. Bad part is that the all future revenues from human
diagnostics will go to Roche. Good part is that PacBio can now bank on the
established marketing machine of Roche.

3\. Here is the most important part. If we estimate that PacBio spends ~$20M
of that money every year on Roche-related development, about 86 employees (out
of ~342) of PacBio will be tied to human diagnostics-related work at $230K run
rate. That is a substantial chunk of the employees and very likely the
experienced ones will go to this important project. Even if PacBio hires a few
newbies, those new employees are not likely to be as skilled as the
experienced crew.

I hope PacBio continues to update their very informative github pages like
before.

