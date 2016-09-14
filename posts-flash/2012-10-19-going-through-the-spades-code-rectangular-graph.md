---
title: Going Through the SPAdes Code (Rectangular Graph)
tags: []
categories:
- blog
---
We finished understanding the algorithms discussed in three SPAdes papers and
find them fascinating.
<!--more-->

i) The main paper titled "SPAdes A New Genome Assembly Algorithm and Its
Applications to Single-Cell Sequencing",

ii) Rectangle graph paper - "From de Bruijn Graphs to Rectangle Graphs for
Genome Assembly",

iii) Pathset graph paper - "Pathset Graphs A Novel Approach for Comprehensive
Utilization of Paired Reads in Genome Assembly".

Before we discuss the algorithms here, we would like to explore the SPAdes
code to complete our understanding. As we work through the code, we will post
our notes on [this thread of the
forum](http://www.homolog.us/smf/index.php?topic=66.0). That way, we can share
what we are doing while keeping the blog clean. There are many C++ files, and
we chose a subset that are the most important to start with IMHO. Here is the
list -

In the **debruijn** directory under src:

> debruijn/repeat_resolver.hpp

debruijn/utils.hpp

debruijn/long_contigs/path_utils.hpp

debruijn/statistics.hpp

debruijn/debruijn_stats.hpp

debruijn/config_struct.hpp

debruijn/graphio.hpp

debruijn/internal_aligner.hpp

debruijn/long_contigs/extend.hpp

debruijn/repeat_resolving_routine.hpp

debruijn/graph_simplification.hpp

debruijn/path_set.hpp

debruijn/long_contigs/paths.hpp

debruijn/long_contigs/lc_common.hpp

debruijn/gap_closer.hpp

In the **include** directory:

>

include/cuckoo.hpp

include/runtime_k.hpp

**sequence:**

include/sequence/seq.hpp

include/sequence/rtseq.hpp

**omni:**

include/omni/mf_ec_remover.hpp

include/omni/tip_clipper.hpp

include/omni/visualization_utils.hpp

include/omni/edges_position_handler.hpp

include/omni/omni_tools.hpp

include/omni/erroneous_connection_remover.hpp

include/omni/splitters.hpp

include/omni/paired_info.hpp

include/omni/omni_utils.hpp

Also, they have a separate folder for 'hammer' and 'quake' error-correction
codes that we are staying away from for the time being. If you like to take a
look, please feel free to explore these programs -

> hammer/quake_correct/edit.cpp

hammer/kmer_cluster.cpp

hammer/quake_correct/Read.cpp

hammer/quake_correct/correct.cpp

hammer/hammer_tools.cpp

The above lists are subject to change as we understand better. After
completing our work, we will post a blog commentary summarizing our
understanding of the files.

