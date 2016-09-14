---
title: Lane-by-lane Sequencing Using Illumina's Genome Analyzer II
categories:
- chem
---
We came across this [cool paper from
2013](http://www.biotechniques.com/BiotechniquesJournal/2013/May/Lane-by-lane-
sequencing-using-Illuminas-Genome-Analyzer-II/biotechniques-343075.html).
<!--more-->

> Next-generation sequencing has become an essential tool in molecular biology
that has been successfully applied to a broad variety of experimental
approaches. While several platforms for next-generation sequencing exist, the
most commonly used approach is sequencing-by-synthesis, implemented on
Illumina's Genome Analyzer II (GAII) and HiSeq2000 systems. A key constraint
of these sequencers is the need to run multiple lanes of samples with
identical parameters as part of a single flowcell. Here, we present a series
of modifications to the Illumina Genome Analyzer II, along with a script
generating tool, that allow users to run the GAII in a lane-by-lane manner.
Any number of lanes can be run at one time. Repeated use of the same flowcell
on multiple sequencing runs does not appreciably reduce the intensity, cluster
density, or accuracy of the run. These modifications will enable smaller-scale
experiments with unusual design parameters to be run routinely on the GAII.

Here is the main method -

> Clustering

Lane-by-lane clustering is performed on the Illumina cBot. Clustering kits
(Part# GD-3002001 and PE-3002001 for single read and paired-end, respectively,
Illumina, Inc., San Diego, CA) were modified by labeling reagent tubes with
their reagent number. Tubes corresponding to unused lanes were cut away while
frozen (Figure 1a). Unused reagents can be stored frozen for future runs.
Empty wells on the reagent plate were replaced with tube strips (Part#
MP73004L, Nova Biostorage Plus, Canonsburg, PA) filled with high salt buffer
(Solution PR1 in all SBS kits for the Genome Analyzer, Illumina, Inc.) to
prevent dehydration of the f lowcell. Lane 1 was always included in the first
set of lanes clustered on a given f lowcell to permit edge-finding and tilt-
setting.

We have modified Illumina's GAII to run partial flowcells through minor
changes in the instrument and fluidics scripts. These changes are suited for
rapid protocol prototyping and sequencing experiments with unusual chemistry
requirements.

Imaging

Imaging was limited to desired lanes in order to reduce run time. The XML
recipe files were edited to remove the Lane Index line entry for each unused
lane under the TileSelection header (Figure 1b). Note that while this does not
prevent the brief imaging during calibration, full within-read imaging is
restricted to the active lanes. Reagent delivery

In order to preserve high signal-to-noise ratios during longer runs, salt
solution in the inactive lanes was removed. Prior to each read, deionized
water was flushed across the entire flowcell while the reagent manifold was
still in the standard configuration, pre-charging the inactive lanes with
salt-free medium.

Following the water wash, reagent flow was physically limited to the desired
lanes by inactivating the pumps corresponding to the unused lanes. The plunger
ends of the syringe-pumps for the unused lanes were disconnected from the
motorized crossbar by removing the connecting screws while in the top position
(Figure 1c).

The reagent delivery volume settings were changed to compensate for the effect
of fewer pumps on rates of flow.

