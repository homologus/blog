---
title: Using Hadoop for Transcriptomics - An Example to Get Started
tags:
- K-mer
- hadoop
categories:
- blog
---
In [our previous commentary](http://www.homolog.us/blogs/2011/08/08/using-
hadoop-for-transcriptomics/), we explained the advantages provided by Hadoop
in distributed analysis of large data sets. Today we will work on a real life
problem, namely, finding all K-mers in a set of short reads. [Being true to
our style](http://www.homolog.us/blogs/2011/08/04/using-r-for-transcriptome-
analysis-i/) (standing on the shoulder of giants), we shall only explain
things that are not explained elsewhere in the web by other experts. When
others have done better job than we can ever do, we are content with providing
links.
<!--more-->

Hadoop is a framework developed primarily for Java programmers. Those, who
have familiarity with Java or C++ but never used Hadoop, will find the
following example the most useful. Others will learn the general concepts, but
may have to do a bit of work, if they want to port our code to their favorite
languages. **It is possible to write Hadoop codes in python** by using [APIs
developed for python](http://www.michael-noll.com/tutorials/writing-an-hadoop-
mapreduce-program-in-python/).

Let us get started. Finding all K-mers from a large set of sequences using
Hadoop requires two steps - (i) installing Hadoop or finding computers where
Hadoop is already installed, and (ii) writing, compiling and running Java code
for the problem at hand. If you follow the example presented here
mechanically, you should be able to install and run the code in Hadoop in less
than 30 minutes. Then the hard work is to understand all the steps.

We tested our code in Windows (cygwin) and Linux (Fedora release 9, 64 bit),
and encountered every possible pitfall a human being could possibly come
across. Hopefully, you will not make the same mistakes as us, but if you do,
the 'Pitfalls' section in the next commentary will be helpful. [The Hadoop
documentation](http://hadoop.apache.org/common/docs/current/index.html)
written by Apache foundation is another excellent source of information, and
we urge you to read it. One point of caution - some examples provided in the
official documentation are not updated for the latest version of Hadoop. We
will mention those differences in our 'Pitfalls' section.

**i) Installing Hadoop**

In our work, we used hadoop-0.20.2 that can be downloaded from
[here](http://apache.tradebit.com/pub/hadoop/common/hadoop-0.20.2/) or
[here](http://www.apache.org/dyn/closer.cgi/hadoop/common/). We encountered
some difficulties with a newer version - hadoop-0.20.203. Please check
'Pitfalls' section for details.

Hadoop is meant to be run in a computer cluster in distributed manner, but one
can also [set it up on a single node in standalone or pseudo-distributed
manner](http://hadoop.apache.org/common/docs/current/single_node_setup.html).
Our example will be based on single node standalone installation. Although
single node operation does not take any advantage of Hadoop, it is great for
testing codes and learning the general concepts. The Java code itself need not
be changed for running it in a distributed cluster. We expect that you will
not have to install Hadoop in a cluster, and you will find help from either
your local computer administrator or [Amazon
cloud](http://aws.amazon.com/elasticmapreduce/). If you have to do multi-node
installation, [Apache documentation](http://hadoop.apache.org/common/docs/curr
ent/cluster_setup.html) is an excellent place to get started.

Please follow these steps for standalone installation of Hadoop -

a) Make sure Java is installed properly in your machine by compiling ('javac')
and running ('java') HelloWorldApp.java from [here](http://download.oracle.com
/javase/tutorial/getStarted/application/index.html). You will see 'Hello
World' printed on your screen.

b) Download stable version of Hadoop from an [Apache Download
Mirror](http://www.apache.org/dyn/closer.cgi/hadoop/common/). We used
hadoop-0.20.2.tar.gz.

c) Uncompress and untar the hadoop-0.20.2.tar.gz file. Your installation is
complete. No need to do 'configure', 'make', etc. It is that easy (thanks to
Java).

d) At this point, you will have 'hadoop-0.20.2' folder in your directory. Go
inside 'hadoop-0.20.2' folder and run 'ls'. You will see the following files
and folders.

![](http://www.homolog.us/blogs/wp-
content/uploads/2011/08/Capture6-300x21.png)

Hadoop executable is located in the 'bin' directory.

The 'txt' files are for general information.

The 'jar' files are compiled versions of various codes and libraries that we
will use for testing and building our own code.

The 'lib' directory has additional libraries.

The 'conf' directory has configuration files.

The 'docs' directory has a copy of Apache documentation that you will find
useful, if you are stuck in Yellowstone NP without any internet.

The 'src' directory has various source-codes. Among them, you can check the
'src/examples' for many excellent Hadoop examples.

e) Edit the file conf/hadoop-env.sh to make 'JAVA_HOME' to be the root of your
Java installation. Alternatively, you can also define JAVA_HOME as an
environment variable from you .cshrc or .bashrc file.

f) From inside 'hadoop-0.20.2' directory, run the following commands.

% mkdir input

% cp conf/*.xml input

% bin/hadoop jar hadoop-0.20.2-examples.jar grep input output 'This'

% cat output/*

In the above steps, you executed an example provided by Hadoop creators. You
copied the content of 'conf' directory to 'input', ran the example in the jar
file 'hadoop-0.20.2-examples.jar' to count number of word 'This' within all
files of 'input' directory. The output of your run is stored in 'output'
directory.

Here is term-by-term explanation of the command on third line (bin/hadoop jar
hadoop-0.20.2-examples.jar grep input output 'This').

bin/hadoop - hadoop executable

jar - option to hadoop executable that tells it that we are running a jar file

hadoop-0.20.2-examples.jar - the jar file being run

grep - class within jar file that is run

input - location of input files

output - location of output files

If we can create a jar file for our K-mer application, we can run it in the
same manner to find all K-mers in a set of sequences. That is explained in the
next section.

**ii) Code for finding all K-mers from a short read library**

If you never used Hadoop, a Hadoop code may appear daunting. We will make the
task real easy for you. We suggest that you learn Hadoop coding in two steps.

Below we included a Hadoop 0.20 template (borrowed from [this
link](http://cxwangyi.blogspot.com/2009/12/wordcount-tutorial-for-
hadoop-0201.html)) that can be used for most simple codes. You can cut and
paste the template, and fill up few sections with code for your favorite
application. You will have to fill up the class names (1,2,3) and add codes
for map and reduce functions. The code for K-mer application in the next
section shows how to do that.

\----------------------------------------

`

package us.homolog;

import java.io.IOException;

import java.lang.InterruptedException;

import java.util.StringTokenizer;

import org.apache.hadoop.io.IntWritable;

import org.apache.hadoop.io.Text;

import org.apache.hadoop.conf.Configuration;

import org.apache.hadoop.fs.Path;

import org.apache.hadoop.mapreduce.Job;

import org.apache.hadoop.mapreduce.Mapper;

import org.apache.hadoop.mapreduce.Reducer;

import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;

import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;

import org.apache.hadoop.util.GenericOptionsParser;

public class ____1____

{

public static class ___2___ extends Mapper

{

INSERT CODE HERE

public void map(Object key, Text value, Context context)

throws IOException, InterruptedException

{

INSERT CODE HERE

context.write(.....);

}

}

public static class ___3___ extends Reducer

{

public void reduce(Text key, Iterable values, Context context)

throws IOException, InterruptedException

{

INSERT CODE HERE

context.write(.....);

}

}

public static void main(String[] args) throws Exception

{

Configuration conf = new Configuration();

String[] otherArgs = new GenericOptionsParser(conf, args).getRemainingArgs();

Job job = new Job(conf, "Example Hadoop 0.20.1 Split Fasta");

job.setJarByClass(___1___.class);

job.setMapperClass(____2__.class);

job.setReducerClass(___3___.class);

job.setOutputKeyClass(Text.class);

job.setOutputValueClass(IntWritable.class);

FileInputFormat.addInputPath(job, new Path(otherArgs[0]));

FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

System.exit(job.waitForCompletion(true) ? 0 : 1);

}

}

`

\----------------------------------------

Here is the code for K-mer application. We used the template and filled the
map and reduce functions. The map function goes through the sequences one by
one and extracts all K-mers (K=10). The reduce function takes outputs of map
function from various files as key-value pairs and adds up the counts.

\----------------------------------------

`

package us.homolog;

import java.io.IOException;

import java.lang.InterruptedException;

import java.util.StringTokenizer;

import org.apache.hadoop.io.IntWritable;

import org.apache.hadoop.io.Text;

import org.apache.hadoop.conf.Configuration;

import org.apache.hadoop.fs.Path;

import org.apache.hadoop.mapreduce.Job;

import org.apache.hadoop.mapreduce.Mapper;

import org.apache.hadoop.mapreduce.Reducer;

import org.apache.hadoop.mapreduce.lib.input.FileInputFormat;

import org.apache.hadoop.mapreduce.lib.output.FileOutputFormat;

import org.apache.hadoop.util.GenericOptionsParser;

public class Kmer

{

public static class KmerMapper extends Mapper

{

private final static IntWritable one = new IntWritable(1);

private Text word = new Text();

public void map(Object key, Text value, Context context)

throws IOException, InterruptedException

{

String line=value.toString();

String sub;

for(int i=0; i<=line.length()-10; i++)

{

sub=line.substring(i,i+10);

word.set(sub);

context.write(word, one);

}

}

}

public static class KmerReducer extends Reducer

{

public void reduce(Text key, Iterable values, Context context)

throws IOException, InterruptedException

{

int sum = 0;

for (IntWritable value : values)

{

sum += value.get();

}

context.write(key, new IntWritable(sum));

}

}

public static void main(String[] args) throws Exception

{

Configuration conf = new Configuration();

String[] otherArgs = new GenericOptionsParser(conf, args).getRemainingArgs();

Job job = new Job(conf, "Example Hadoop 0.20.1 Kmer");

job.setJarByClass(Kmer.class);

job.setMapperClass(KmerMapper.class);

job.setReducerClass(KmerReducer.class);

job.setOutputKeyClass(Text.class);

job.setOutputValueClass(IntWritable.class);

FileInputFormat.addInputPath(job, new Path(otherArgs[0]));

FileOutputFormat.setOutputPath(job, new Path(otherArgs[1]));

System.exit(job.waitForCompletion(true) ? 0 : 1);

}

}

`

\----------------------------------------

Instructions on how to compile and run the above code are given below.

Create a folder named Kmer in your main directory and save the above code as
Kmer.java inside the folder. You already have another folder hadoop-0.20.2 in
your main folder with all Hadoop files.

Go inside Kmer folder and run the following commands.

% mkdir kmer_classes

% javac -classpath
../hadoop-0.20.2/hadoop-0.20.2-core.jar:../hadoop-0.20.2/lib/commons-
cli-1.2.jar -d kmer_classes Kmer.java

% jar -cvf Kmer.jar -C kmer_classes/ .

The above steps will create the Kmer.jar and we already know how to run it
using Hadoop in standalone mode.

% mkdir input

% echo 'ATATATATATATATAT' > input/seq-W-strand

% echo 'ATATATATATATATAT' > input/seq-C-strand

% ../hadoop-0.20.2/bin/hadoop jar Kmer.jar us.homolog.Kmer input output

% cat output/*

You will see that our input file has 8 ATATATATAT and 6 TATATATATA.

Regarding data format, the files in 'input' directory should have all read
sequences with one sequence/line. They are not in FASTA format. We also
generated reverse complements ourselves and added them in a separate file. You
can split the reads and reverse complements in as many files within the
'input' folder as you want. There is no need to preserve order.

If you followed the above code, a good homework is to modify it for reverse
complement. Another exercise is to make it read FASTA-formatted inputs.

Additional posts on the same topic -

[Hadoop Example - FAQ](http://www.homolog.us/blogs/2011/09/05/hadoop-example-
faq/)

[Contrail - A de Bruijn Genome Assembler that uses
Hadoop](http://www.homolog.us/blogs/2011/09/08/contrail-a-de-bruijn-genome-
assembler-that-uses-hadoop/)

