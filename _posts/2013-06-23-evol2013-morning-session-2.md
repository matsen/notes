---
layout: post
title:  "Evolution 2013: Morning session II"
date:   2013-06-23 10:30:00
categories: Evolution2013
---

## Lachance, Joseph; Tishkoff, Sarah: Scans of selection using whole genome sequences of diverse African hunter-gatherers reveal associations between pituitary loci and Pygmy stature

Pygmies admixed with Bantu.
More Pygmy genetics -> shorter.
15 genomes, 60X coverage: Has, Sanawe, and Pygmy.
Also

Locus specific branch length statistic (LSBL).
Looking for long branch length going to Pygmy.
100Kb sliding windows.
See some interesting differenes with Pygmies: find putuitary gland differences.
However, European GWAS hits didn't come out.

Now look for Ancestry Informative Markers (AIMs)-- only found in
These are not randomly distributed along genome.
Not due to common ancestry.
See correlation between LSBL and AIMs.
See some reasonable candidate clusters.

Go back and get SNPs from one of these interesting clusters.
See same haplotype in two divergent lineages of Pygmies.
Find association with height and these SNPs.
But this could be due to ancestry.

EMMAX uses an identity by state matrix to learn about if these SNPs are significant above ancestry.
See Hesx1 changes-- it's a master regulator of development.
Pygmies have a missense mutation in a non-coding region.

Tishkoff lab.


## Howard Ross: Reassessing species-level paraphyly in Animals

Funk and Omland (2003) show high incidence of para- and polyphyly.

He going to re-evaluate this.
Multiple sources that can lead to this-- taxonomic practice and molecular history.

Take a big data set. Some filtration-- only allowing genera that don't have badly named things.
Midpoint rooting and BME-- but trying other methods doesn't matter.

He finds slightly less paraphyly than Funk and Omland.

Could this be from mislabeling?
Perhaps-- this halves the putative number of paraphyletic species.

What about missing species-- don't know, but do have apparent increase in paraphyly with sampling effort.

For the most part, confirming Funk and Omland.


## Linderoth, Tyler; Nielsen, Rasmus: A likelihood method for detecting paralogy from next-generation sequencing data

Going to be infestigating paralogy.
At least 15% of protein coding genes are from duplication.
Are powerful regions for detecting selection.

Example.
Two loci-- can accrue segregating mutations.
NGS.
Get read stacks-- often times paralogous sequences stacked on top of one another.

Can deal with this using deviation from H-W.
Or can think about it as an admixture problem.
Assuming that we know what is derived and that only one locus is variable.
What is the probability of a derived allele given the genotype configuration.

Real data: exon capture on chipmunks.
Paralogs show up as a spike in the site frequency spectrum.
His method removes it.
Sees spike in the MHC region for duplication.


## Heled, Joseph: Building REALLY Big Trees

Little Barrier Island study: Genomics for Ecosystem conservation.
Sequencing ITS from soil samples.
Relatively short-- lots of 200-300bp.
Non-coding, and self duplicates.

Use USEARCH to cluster at 1%, and 3% clusters used as OTUs.
Lots of polyphyly.
Seemes like a problem-- can we

Now build a "real" tree-- can't align.
Use JC correction for distances -> UPGMA.

Showing evidence of problems with USEARCH heuristics.

"Clustering is a sport."

* Declutter: divide sequences into subsets of of manageable size. Put dissimilar things in different bins.
* Build trees with UPGMA
* Knit them back together. Because UPGMA is ultrametric, can take a subset of sequences, build a bigger tree, then knit back together.

Can see a whole continuum of richness and diversity at any distance groupings.
In particular, can look beyond first drop which appears to be sequencing error.
Perform taxonomic classification by tree inclusion.



