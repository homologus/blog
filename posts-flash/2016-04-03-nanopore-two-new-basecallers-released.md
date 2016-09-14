---
title: Nanopore - Two New Basecallers Released
tags: []
categories:
- blog
---
David Eccles, who [provides excellent
update](http://www.homolog.us/blogs/blog/2014/10/19/nanopore-updates-from-
david-eccles/) on the latest advances related to Oxford Nanopore technology,
pointed out that two new open source base-callers have been released last
week. So far the researchers relied on the proprietary software provided by
Oxford Nanopore, and that required having internet connection in remote
locations. It is also noteworthy that at least the second paper claims to
improve basecalling accuracy ("By employing carefully crafted recurrent neural
networks, our tool improves the base calling accuracy compared to the default
base caller supplied by the manufacturer."). Overall, these are very exciting
times in the sequencing world.
<!--more-->

[Nanocall: An Open Source Basecaller for Oxford Nanopore Sequencing
Data](http://www.biorxiv.org/content/early/2016/03/28/046086)

> Motivation: The highly portable Oxford Nanopore MinION sequencer has enabled
new applications of genome sequencing directly in the field. However, the
MinION currently relies on a cloud computing platform, Metrichor
(metrichor.com), for translating locally generated sequencing data into
basecalls. Results: To allow offline and private analysis of MinION data, we
created Nanocall. Nanocall is the first freely-available, open-source
basecaller for Oxford Nanopore sequencing data and does not require an
internet connection. On two ecoli and two human samples, with natural as well
as PCR-amplified DNA, Nanocall reads have ~68% identity, directly comparable
to Metrichor "1D" data. Further, Nanocall is efficient, processing ~500Kbp of
sequence per core hour, and fully parallelized. Using 8 cores, Nanocall could
basecall a MinION sequencing run in real time. Metrichor provides the ability
to integrate the "1D" sequencing of template and complement strands of a
single DNA molecule, and create a "2D" read. Nanocall does not currently
integrate this technology, and addition of this capability will be an
important future development. In summary, Nanocall is the first open-source,
freely available, off-line basecaller for Oxford Nanopore sequencing data.
Availability: Nanocall is available at github.com/mateidavid/nanocall,
released under the MIT license. Contact: matei.david at oicr.on.ca

[DeepNano: Deep Recurrent Neural Networks for Base Calling in MinION Nanopore
Reads](http://arxiv.org/abs/1603.09195)

> Motivation: The MinION device by Oxford Nanopore is the first portable
sequencing device. MinION is able to produce very long reads (reads over
100~kBp were reported), however it suffers from high sequencing error rate. In
this paper, we show that the error rate can be reduced by improving the base
calling process.

Results: We present the first open-source DNA base caller for the MinION
sequencing platform by Oxford Nanopore. By employing carefully crafted
recurrent neural networks, our tool improves the base calling accuracy
compared to the default base caller supplied by the manufacturer. This advance
may further enhance applicability of MinION for genome sequencing and various
clinical applications.

Availability: DeepNano can be downloaded at this http URL

Contact: boza@fmph.uniba.sk

