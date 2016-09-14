---
title: Michael Huss Provides Introduction to Three Commercial Genomic APIs
tags: []
categories:
- blog
---
In his informative blog, our reader Michael Huss is writing three posts
describing genomics APIs from various companies. Two of them are already
posted.
<!--more-->

**Notes on genomics APIs #1: One Codex**

> [One Codex](https://onecodex.com/) calls itself a genomic search engine,
enabling new and valuable applications in clinical diagnostics, food safety,
and biosecurity. They have built a data platform where you can rapidly (much
more quickly than with e.g. BLAST) match your sequences against an indexed
reference database containing a large collection of bacterial, viral and
fungal genomes. They have a good web interface for doing the search but have
also introduced an API. I like to use command-line APIs in order to wrap
things into workflows, so I decided to try it. Here are some notes on how you
might use it.

This service could be useful when you want to identify contamination or
perhaps the presence of some infectious agent in a tissue sample, but the most
obvious use case is perhaps for metagenomics (when you have sequenced a mixed
population of organisms). Lets go to to the EBI Metagenomics site, which keeps
a directory of public metagenomics data sets. Browsing through the list of
projects, we see an interesting looking one: the Artisanal Cheese Metagenome.
Lets download one of the sequence files for that. Click the sample name
(Artisanal cheeses), then click the Download tab. Now click Submitted
nucleotide reads (ENA website). There are two gzipped FASTQ files here I
arbitrarily choose to download the first one [direct link]. This download is
353 Mb and took about 10 minutes on my connection. (If you want a lighter
download, you could try the 100 day old infant gut metagenome which is only
about 1 Mb in size.)

Continue reading [here](https://followthedata.wordpress.com/2015/02/03/notes-
on-genomics-apis-1-onecodex/).

\-----------------------------

[Notes on genomics APIs #2: Google Genomics
API](https://followthedata.wordpress.com/2015/02/05/notes-on-genomics-apis-2
-google-genomics-api/)

> As you may have heard, Google has started building an ambitious
infrastructure for storing and querying genomic data, so I was eager to start
exploring it. However, as there were a number of tools available, I initially
had some trouble wrapping my head around what I was supposed to do. I hope
these notes, where I mainly use the API for R, can provide some help.

Some useful bookmarks:

Google Developers Console for creating and managing Google Genomics and
BigQuery projects.

Google Genomics GitHub repo

Google Cloud Platform Google Genomics page (not sure what to call this page
really)

Continue reading [here](https://followthedata.wordpress.com/2015/02/05/notes-
on-genomics-apis-2-google-genomics-api/).

\-----------------------------

Notes on genomics APIs #3: SolveBio

> SolveBio delivers the critical reference data used by hospitals and
companies to run genomic applications, according to their web page. They focus
on clinical genomics and on helping developers who need to access various data
sources in a programmatic way. Their curated data library provides access to
(as of February 2015) over 300 datasets for genomics, proteomics, literature
annotation, variant-disease relationships, and more.) Some examples of those
datasets are the ClinVar disease gene database from NIH, the Somatic Mutations
dataset from The Cancer Genome Atlas, and the COSMIC catalogue of somatic
mutations in cancer.

Continue reading [here](https://followthedata.wordpress.com/2015/02/07/notes-
on-genomics-apis-3-solvebio/).

