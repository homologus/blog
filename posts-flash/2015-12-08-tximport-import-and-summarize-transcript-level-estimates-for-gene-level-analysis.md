---
title: 'tximport: import and summarize transcript-level estimates for gene-level analysis'
categories:
- rnaseq
---
https://github.com/mikelove/tximport/blob/master/vignettes/tximport.md
<!--more-->

> kallisto

First, read in some kallisto example files:

library(tximportData)

dir <\- system.file("extdata", package="tximportData")

list.files(dir)

## [1] "cufflinks" "gene2tx.csv" "kallisto" "rsem" "salmon"

## [6] "samples.txt" "tmp"

samples <\- read.table(file.path(dir,"samples.txt"), header=TRUE)

files <\- file.path(dir,"kallisto", samples$run, "abundance.tsv")

names(files) <\- paste0("sample",1:6)

Transcripts need to be associated with gene IDs for summarization. If that
information is present in the files, we can skip this step. But for kallisto
and Salmon, the files just provide the transcript ID. So we first make a
data.frame with two columns: gene ID (column 1) and transcript ID (column 2).
The column names are not relevant but this column order must be used. This can
be accomplished from a TxDb object and the select function. (TODO: show
example)

