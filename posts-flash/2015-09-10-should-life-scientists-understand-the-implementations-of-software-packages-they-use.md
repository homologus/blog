---
title: Should Life Scientists Understand the Implementations of Software Packages
  They Use?
tags: []
categories:
- blog
---
We received plenty of requests for the "[Scripting for Biology -
1](http://www.homolog.us/blogs/blog/2015/09/01/scripting-for-biology-online-
virtual-classroom-based-module/)" class. Since a real person will work with
students in the virtual classroom, we are keeping the class size limited to
10. Therefore, we decided to add an October session and requested some
students to join that module. There are couple of spots left for the October
session, and if you like to join, please email pandora at homolog.us.
<!--more-->

\-----------------------------------------------

**Why this scripting module?**

We have been building a number of bioinformatics modules on - (i) [dBG-based
assembly algorithms](https://leanpub.com/NGS-assembly), (ii) RNAseq analysis,
(iii) metagenomics, (iv) [Pandora's toolbox](https://leanpub.com/pandoras-
toolbox) and (v) Pacbio/long-read assembly and analysis. In our design, we
like to break out of conventional method, where bioinformatics students are
taught how to run software packages. In our method, we like to cover
algorithms, programs and a bit of implementation for each program instead of
only describing the program. For example, for RNAseq quantification, we like
the students to understand the expectation-maximization process and not just
learn to use relevant programs as black-boxes. In order to do that, we feel
the students need to know a bit of scripting.

That brings us to the $64M question - should life scientists really need to
know, how the programs work in order to use them effectively?

\-----------------------------------------------

**Should Life Scientists Understand the Implementations of Software Packages They Use?**

I think it is absolutely necessary. When I say that, I hear many counter-
examples from other areas. In the internet world, people are doing fine with
web-browsers without learning all details about http protocol. Also, everyone
is using iphone perfectly well without getting a degree in electrical
engineering. Then why is bioinformatics different? Here is a short answer.

Each packaged software hides one (or more) of three aspects - hardware,
(digital) algorithm or statistics. For example, a web browser hides computer
and network hardware. Through your browser, you are requesting a page from a
remote computer, bringing it to your computer and reading it. A sorting
program hides algorithm. You can run 'sort' or 'grep' from unix command line
without worrying about how the programs are implemented, because the results
are identical in all implementations.

Those two categories are different from a package that hides statistics.
Statistics is the primary basis of the claims made by researchers in their
papers, and therefore making a strong claim like 'we show in this paper'
requires the researcher to think through all statistical implications of
various software tools. How can one do that, if some of the statistical tools
are black-boxes? By black-box, I do not mean they are closed-source, but
whether the person writing paper understands the parameters and
implementations of open-source packages.

At a more philosophical level, the underlying Nature is analog, and this
analog world is what a life scientist tries to understand through research.
The digital technologies, on the other hand, make an abstraction of this
analog Nature, and their packages hiding hardware or algorithm usually stay
within that abstracted digital domain. However, a bioinformatics package
hiding statistics tries to make connection all the way to the analog world,
and should not be treated in the same way as a web browser or Amazon shopping
app.

