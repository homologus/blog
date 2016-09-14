---
title: HDF5 Data Format for PacBio Sequences
tags: []
categories:
- blog
---
Few days back, we discussed [SQL database and other hard-disk-based storage
methods](http://www.homolog.us/blogs/2012/06/08/nosql-databases-for-
bioinformatics/) for storing and accessing large de Bruijn graphs. In the
comments section, several readers directed us to recently published algorithms
to load de Bruijn graphs in significantly less RAM space than usual. Those
methods do alleviate the problem of dealing with large de Bruijn graphs.
However, the question of rapid data access from hard-drive comes to the minds
of bioinformaticians in other contexts, such as for storing and loading large
genome assemblies. HDF5 is a data format designed by National Center for
Supercomputing Applications at UIUC to rapidly access large scientific data
sets.
<!--more-->

Long story short, our Pac Bio raw reads came in the HDF5 format and so we had
no other option than to start looking for the best tools to process them. We
will briefly write down what we found (without too much explanation) so that
you can save some time searching through the web.

**Q. What is HDF?**

HDF stands for Hierarchical Data Format. If those three words do not mean much
to you, [wiki](http://en.wikipedia.org/wiki/Hierarchical_Data_Format) has the
best explanation of what they mean.

**Q. Cannot we just stick the data into SQL databases instead of going through all the trouble of learning a new format?**

SQL database and HDF solve two different problems. HDF is for very large data
sets that have some kind of uniform structure. For example, let us say you
have 500 Gb of sequences in FASTA format with average sequence length of 5000
nucleotides. Storing the data in SQL database and running the access commands
in client-server mode reduces speed of access. So, it is preferable to store
the entire data set in hard drive and access locally. HDF works well on such
data. It used [B-TREE](http://en.wikipedia.org/wiki/B-trees)s to index the
data sets.

On the other hand, let us say you have 20 different data sets with genes,
expression information in five tissues, functional annotation, homology with
other organisms, etc. and you like to ask questions such as 'which gene is
present in human and mouse, expressed in human liver but not expressed in
mouse brain, and has some keyword match with cancer'. SQL works better for
such complex queries.

**Q. What is HDF5?**

It is much improved version of original HDF format.

1\. The best source to learn about the format is [HDF5
group](http://www.hdfgroup.org/HDF5/).

2\. User guide located
[here](http://www.hdfgroup.org/HDF5/doc/UG/UG_frame03DataModel.html) describes
C APIs to read HDF5 files.

3\. If you use R, there is already a [package named
pdh5](https://github.com/PacificBiosciences/R-pbh5) to interact directly with
various PacBio libraries (suggested by reader Jim). Also, the [package
h5r](http://cran.r-project.org/web/packages/h5r/index.html) suggested by
readers Mengjuei Hsieh and Jim should be helpful. We originally identified
[hdf5 package in R](http://cran.r-project.org/web/packages/hdf5/index.html) to
read HDF5 files, but the other two suggestions may be better.

4\. If you use python, please try [this
source](http://code.google.com/p/h5py/).

We also found [this
source](http://beige.ucs.indiana.edu/I590/node119.html#3941) helpful.

**Q. I am a PERL user. What should I do? 

**

<del>Please google 'go hang yourself' and follow any of the links.</del>

[Here](http://search.cpan.org/~cerney/PDL-IO-HDF5/HDF5/Dataset.pm ) is a Perl
alternative to deal with HDF5 format [Thanks Inti Pedroso.]

