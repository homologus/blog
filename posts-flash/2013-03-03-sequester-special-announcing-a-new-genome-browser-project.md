---
title: Sequester Special - Announcing a New Genome Browser Project
tags: []
categories:
- blog
---
We wish we do not have to do this, because we are incredibly swamped with
genome and transcriptome assembly projects, algorithm development and other
work. However, no matter how hard we look around, we cannot find a web-based
genome browser that solves our problems. Please talk us out of months of
coding by showing an example that we can use. The kids will thank you, when
they grow up !!
<!--more-->

**Features**

Here are the features we are looking for in our to-be-favorite genome browser.

1\. It should self-install through few clicks in any web folder that we place
the zip file in. We do not enjoy installing PERL modules, solving
dependencies, and we do not want to see the word 'cgi-bin' in year 2013. We
did not like cgi-bin even in 1998.

2\. It should display genes and genome at various resolutions, and should move
very smoothly like Google map. Also, it should do google map-type synchronous
move for multiple genomes. Nobody works with a single organism any more.

3\. It should have an admin module to set various levels of data access
permissions for various users and groups. Some data sets will be public, some
will be private for user A and B, some will be private for user C and D. We
work with many groups, and even among those groups, we have subgroups with
different interests. The bioinformaticians working on computational cleaning
up of genes want the latest edition of genes. The biologists digging through
data want more stable release.

4\. It should have modular code so that anyone can add features easily. Want
to add BAM files? Just write a plug-in within the larger code-base. The genome
browser does not have to provide APIs, but some kind of documentation on code
would be very nice.

5\. It should not come with GNU-GPL type license, and God forbid UC style
license (please check [kind of Browsers to
avoid](http://www.homolog.us/blogs/2012/08/11/browsers-for-viewing-ngs-
data/)).

6\. This is a minor point. We like to change the theme easily.

We could not find a single browser that met 1-5, and we are puzzled why.
Outside the bioinformatics world, hundreds of free, open source, high-quality
easy-to-install codes exist for everything from secure shopping cart to
blogging platform or auction site.

We will start our development, and continue until we are done or a high-
quality alternative shows up.

**Design**

Our design will be highly modular. More than writing a genome browser, we like
to design code, whose components can be easily replaced or exchanged. Like the
admin module, but not front end? Feel free to write your own jquery, node.js
and gRaphael.

**License**

Our code will be MIT-licensed. Take it, break it, sell it as a package or do
whatever you want to do with it. We will feel grateful that you use our
browser. Most likely we will be the only user.

**Technology**

Front end or client side will be HTML5+Javascript-based. It will use AJAX to
pull JSON data from server side.

Server code will be PHP-based. We will use a popular MVC framework.

Data side will try to cover all commonly-used databases including MySQL and
postgreSQL.

**Documentation**

Right from start, we plan to create extensive documentation on the code as
well user-functions. We are designing the code to be easily extensible so that
anyone can add feature he wants.

**Funding**

This project is to honor sequester. So, we will NOT seek any kind of
government funding, not now, not in the future. If you like to be a private
sponsor or help us with coding, please feel free to contact at samanta at
homolog.us.

**Timeline**

This is a side project born out of frustration with status quo. Although we
have proof-of-concept code for every feature proposed above, in coding, it
takes a long time to turn proof-of-concepts into something presentable. Expect
things to move very slow except when it moves fast :) We will continue to work
on genome and transcriptome assemblies as our primary project, and come back
to this coding only intermittently, unless there is huge community interest to
see this project moving.

You can track our progress [here at
github](https://github.com/homologus/ScaleViewer), and we will write in the
blog before any beta release or major release.

\----------------------------

Any thoughts or suggestion?

