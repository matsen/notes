---
layout: post
title:  "Evolution 2013: Phylogenomics"
date:   2013-06-25 11:30:00
categories: Evolution2013
---

## Steel, Mike: Lateral gene transfer, and joys of leaping between trees

Even if every gene had been transferred 10 times, he claims that a "species tree" can still be meaningful.

Tree of cell divisions.
Can random LGT lead to statistical inconsistency in estimating this species tree from a collection of gene trees?
When can we infer a species tree from gene tres

Fixing transfer between cherries = "fixed transfer."
For 3 taxon random transfers, 1 out of 3 fixes topology.

Modeling random LGT.
"Vanilla model" independent of where you start and end.
More biologically realistic model would have higher rate of transfer between closely related species.

Easy to show: under model, 3 taxon tree reconstruction is statistically consistent if no other linages are involved.
Key point-- if the first transfer happens before any speciation, that boosts
True for vanilla model and more realistic model.

Harder: what about other taxa present?
Some of these lineages could be extinct.

When a fixing transfer occurs, it is easy to analyze.
However, if we have a non-fixing transfer and then a fixing transfer, that's really hard.

Have a random walk on a graph gives exact equation for the probability of a match for (a,b,c)
Have a small zone of inconsistency for balanced tree only.

There is a triplet-based tree reconstruction is a statistically consistent estimator if the number of transfers is less than n / (3 ln n).
Roch and Snir (2013) show that this is enough to estimate species tree.
This is sharp.
Use "primordial tree" in Dendroscope 3

Future work.
Is "strong" inconcistency, i.e. confidently choosing the wrong topology, possible?
Incorporate error in gene tree estimator.
Identifying a species tree subject to random lateral gene transfer. JTB.
Sand and Steel. Standard lateral transfer is statistically consistent... (submitted).


## Rabier, Charles-Elie; Ta, Tram; Ane, Cecile: Detecting and locating whole genome duplications: a rigorous probabilistic approach

Jiao et al (Nature, 2011) discussing whole genome transfers.

Methods.
Synteny based method: Kellis et al (Nature, 2004).
Age distribution-based method.
Look for collection of paralogous genes that have same timing.
However, very difficult to estimate deep timings.

Jiao et al (Nature, 2011) use a mixture model to infer WGD events using timing events.
Find two major events.

Today: probabilistic WGD model.

* Phylogenetic method dealing with gene tree reonciliation
* Also a gene counting method.

Standard gene-tree species-tree model.
At the WGD, each gene is copied, and the second copy is retained with probability q.

They built a new version of SPIMAP of Rasmussen and Kellis (2011) which deals with WGD.
LRT methods for testing.

Simulation study to compare phylogenetic versus gene counting method.
Phylogenetic method does pretty good estimating retention rate.
Power of method pretty good when high retention rate.

Remarkable: retention rate is well estimated using gene counting method.
Also excellent power to find whole genome duplication.
They can solve it exactly.

Application to yeast data.
Both methods estimate a retention rate of about 0.1, and existence of a WGD.



## Kubinak, Jason L.; Round, June L.: MHC-Microbiota Interactions in Health and Disease

Hypothesis I-- MHC genotype shapes microbiota composition.
See significant differences but ongoing work.

Hypothesis II - HMC microbiota interactions differentially influence gut immune response.
Transfer experiments from different MHC haplotypes.
Transfer and then look at MHC types.
See significant differences- more Tregs.

Hypothesis III-- MHC-mediated disease susceptibility is microbiota-dependent.
Treat with DSS to destroy mucosal layer.
Microbial transfer experiment.
Single genotype mice, and treat with antibiotics.
Some part of disease susceptibility is due to how HMC determines microbial communities.
Application: help figure out good donors for fecal transplant, predict problems.

Take-home: Antagonistic coevolution with microorganisms is though to be a main driver of MHC evolution... but we should think about the mutualists as well.



## Cogni, Rodrigo; Jiggins, Frank: Mapping resistance to naturally coevolving viruses in a genetic model organism (Drosophila melanogaster)

Nuismer et al-- "When is correlation coevolution"?
Need integrative research programs including mechanistic understanding.
Very few complete examples; Stickleback is one of them.

Will be using Drosophila melanogaster versus natural enemies-- viruses and bacteria.
Focus on six viruses.
Some are naturally infectious in the wild, some are not-- brought in lab.

GWAS for each of each of 6 viruses.
200 inbred lines with sequenced genomes.
Measure virus titer and mortaility.

Clear signal of genetic variation to immunity.
Look for heritability.
Coevolving virus shows higher heritability than non-coevolving virus.

Resistance is virus-specific: there is no significant genetic correlation among resistance to different viruses.

GWAS study.
Can see SNPs that are associated with resistance to some specific viruses, not for some others.
Knock-downs to confirm these genetic associations.
See this in the field as well, by genotyping and making
Also see signs of selective sweep for these loci.


## Warnow, Tandy; Bayzid, Shamsuzzoha Md.; Mirarab, Siavash: Naive Binning Improves Phylogenomic Analysis

Gene concatenation among genes with similar signal increases accuracy.
But it's hard to find these ahead of time.
Contatenating random pairs of alignments substantially improves accuracy. (?!)


## Drummond, Alexei; Wu, Chieh-Hsi; Heled, Joseph: Bayesian model averaging and the multispecies coalescent for phylogenomics

BEAST 2 exists, Bayesian model averaging is good, and *BEAST runs are feasible with lots of genes and it's worth it.
