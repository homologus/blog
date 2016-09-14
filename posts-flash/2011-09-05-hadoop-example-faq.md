---
title: Hadoop Example - FAQ
tags:
- K-mer
- hadoop
categories:
- blog
---
Everyone working on next-gen sequence analysis gets hindered by sizes of
sequence libraries quickly overtaking available RAM. We [previously
explained](http://www.homolog.us/blogs/2011/08/08/using-hadoop-for-
transcriptomics/) that using Hadoop is an alternative way to scale for large
data sets, because hard drives are cheaper than RAM. We also gave [an example
](http://www.homolog.us/blogs/2011/08/31/using-hadoop-for-transcriptomics-an-
example-to-get-started/) of simple code and all associated instructions to get
you started with Hadoop. This post is a continuation of previous one listing
few common errors one may encounter. Veteran Java programmers do not need to
bother with this commentary.
<!--more-->

**Q1. I am sure my computer has Java installed, because I keep getting Java updates every few days. However, I cannot compile HelloWorldApp.java. Where is 'javac' compiler located?**

Sun/Oracle releases Java in two parts. JRE (Java Runtime Environment) is
installed in most machines and is used to run Java-based applications on the
web or locally. JDK (Java Development Kit) is a separate module for developers
and can be downloaded from
[here](http://www.oracle.com/technetwork/java/javase/downloads/index.html).
You need to install it to run javac.

**Q2. I downloaded and installed JDK, but still cannot run 'javac'.**

You will either have to include directory for Java sdk in your PATH, or use
the full path in all commands.

**Q3. I followed the instruction on Apache Hadoop manual to run [Wordcount example](http://hadoop.apache.org/common/docs/r0.20.2/mapred_tutorial.html#Example%3A+WordCount+v1.0), but got this error - 

_Note: WordCount.java uses or overrides a deprecated API.

Note: Recompile with -Xlint:deprecation for details._

When I executed with -Xlint:deprecation option, I got 9 warnings.

What should I do?

**

The WordCount example in the manual is based on hadoop 0.18, whereas you are
using Hadoop 0.20.2. That is why the warnings are appearing. The warnings are
harmless for execution of the code, but if you want clean code, you can either
use WordCount example in hadoop-0.20.2/src/examples/org/apache/hadoop/examples
directory, or at [this link](http://cxwangyi.blogspot.com/2009/12/wordcount-
tutorial-for-hadoop-0201.html).

**Q4. I compiled WordCount.java from examples directory using instructions from Apache manual website, but got this error - 

_WordCount.java:53: cannot access org.apache.commons.cli.Options

class file for org.apache.commons.cli.Options not found

String[] otherArgs = new GenericOptionsParser(conf, args).getRemainingArgs();

^

1 error_

What should I do?

**

You need to include cli library in your command. Instead of typing

% javac -classpath hadoop-0.20.2-core.jar -d wordcount_classes WordCount.java

type

% javac -classpath hadoop-0.20.2-core.jar:lib/commons-cli-1.2.jar -d
wordcount_classes WordCount.java

That should work.

**Q5. The above command does not work and I am getting many errors now. I am using windows cygwin.**

In windows/cygwin, you will have to use semi-colon instead of colon to include
multiple libraries. However, unix of cygwin interprets a semi-colon as end of
command. So, you will have to put the entire library statement in quotes.

% javac -classpath "hadoop-0.20.2-core.jar;lib/commons-cli-1.2.jar" -d
wordcount_classes WordCount.java

**Q6. Compilation worked fine, but I am getting this ClassNotFoundException at run time. Why cannot hadoop find my class? 

_Exception in thread "main" java.lang.ClassNotFoundException:
org.myorg.WordCount

at java.net.URLClassLoader$1.run(URLClassLoader.java:202)

at java.security.AccessController.doPrivileged(Native Method)

at java.net.URLClassLoader.findClass(URLClassLoader.java:190)

at java.lang.ClassLoader.loadClass(ClassLoader.java:307)

at java.lang.ClassLoader.loadClass(ClassLoader.java:248)

at java.lang.Class.forName0(Native Method)

at java.lang.Class.forName(Class.java:247)

at org.apache.hadoop.util.RunJar.main(RunJar.java:149)_

**

You did not run the jar command correctly. Remember - you need to include "-C"
before the directory and "." at the end of the statement.

**I got _Error: JAVA_HOME is not set._**

You will have to set environment variable JAVA_HOME to the root directory of
java in your computer. You can do it in your .bashrc directory.

**Q7. I still got an error, because hadoop is not taking "Program Files" with space as one word.**

I solved this by creating a linked directory in cygwin to my "Program Files"
directory, and then calling the link file JAVA_HOME.

**Q8. Hadoop cannot allocate HEAP size of 1000MB in my computer and is giving me error.**

This is a common problem especially in 32 bit windows. You can avoid this for
test programs by opening the file hadoop-0.20.2/conf/hadoop-env.sh and
modifying HADOOP_HEAPSIZE parameter to 200 (MB).

**Q9. Everything is running fine now. Can I buy you a beer? 

**

Certainly !! Email me at samanta at homolog.us and I will show up, when you go
out next time :)

Additional posts on the same topic -

[Using Hadoop for Transcriptomics - An Example to Get
Started](http://http://www.homolog.us/blogs/2011/08/31/using-hadoop-for-
transcriptomics-an-example-to-get-started/)

[Contrail - A de Bruijn Genome Assembler that uses
Hadoop](http://www.homolog.us/blogs/2011/09/08/contrail-a-de-bruijn-genome-
assembler-that-uses-hadoop/)

