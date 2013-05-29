---
layout: post
title:  "Gil McVean: Human genetic variation"
date:   2013-05-29 9:00:00
categories: MCEB2013
---

Charlesworth was his advisor.
"There are no new questions in population genetics."
But we are getting new types of data.
Example of Faroe islands-- government wants to sequence every genome.
UK Biobank-- 500,000 people enrolled-- all sorts of imaging and other test.
Data from multiple species.
Longitudinal data.

How do we think about variation in humans?
Infinite sites model is a pretty good approximation, so we can just use two colors to display.
Can build trees on sequence data, show mutations on tree as dots.

What determines the shape of the tree?
Can think in terms of coalescent.
What happens in the presence of recombination?
We can model it using ARGs.
"ARG is a beautiful beast".

The decay of a tree by recombination- how much of the signal of that tree is kept as we move along the genome.
Clusters of closely related sequences persist, but deep structure changes quickly.
If we did know the tree, we would be able to infer age of mutation, date of population founding, migration and admixture.

Ideally, would like to be able to have the tree at every column.
Donnelly, Fearnhead, Felsenstein, have developed importance sampling and MCMC.
These are computationally intensive-- don't scale.

Valiant attempts to make things faster.
Adam Siepel-- sequentially Markov coalescent.
Also

* Dimension-reduction: projection of the ARG
* Approximate the model (e.g. sequentially Markov coalescent)
* Approximate the likelihood function (e.g. ABC, composite likelihood)

Composite likelihood approximation.
Take pairs of sites, and calculate log likelihood.
Combine information across all of the given pairs.
Composite gives decent approximation to likelihood function.

We would like to infer recombination rates.
Use RJMCMC.
Random walk on piecewise constant recombination rates.

* Q: Do you really take all pairs?
* A: No. Limit the maximum distance between pairs. It turns out that this limited-distance approximation is consistent, where the original one is not.

Fine-scale validation of the method: (McVean et al 2004).
Does a good job.
Broad-scale validation: compare to deCODE pedigree data.

Can use these pedigrees to date haplotypes because length of chunk ~ Gamma(2, 1/TMRCA)
Note that genetic distance is measured in terms of centimorgans-- which makes this work.
Hotspots differ in Africa vs Europe, but still useful.

1000 genomes project.
Actually have 2,500 by now.
Design: sequence all genes to high coverage, dense SNP arrays, between genes low coverage.
Population sequencing: if we have a large population, can infer a good genome from low coverage.

4 million sites that differ from the human reference genome.
12,000 changes to proteins.
100 changes that knockout gene function.
5 rare variants that cause disease.

Most variation is common, relatively old, and common across the world.
92% of the variants you have is found in all continetns.
0.3% is only found in Europe, 0.1% found only in UK.
0.002% found only in you.

Can this tell us about how populations came about?
Application of PCA is fine, but doesn't tell us anything that we want to know, e.g. how far back do we have to go to find common ancestry.
Can directly estimate T_{MRCA} by looking at number of shared mutations.
Assume mutation rate of 1.5e-8/bp/gen and 25 years/gen
1.8MY to universal common ancestor.
China to UK, 0.60 MY.
These are *much* older than origin of anatomically modern humans, and much much older than the time of out of Africa.

* Q: What about slightly deleterious mutations? Does that change this time scale?
* A: It's fine to ignore that. Human populations have been small, and selection effects are small.

Most variants are rare, and most rare variation is very regionally limited.
Low frequency variants.
By 10% frequency most variants are in all continents.

Can use recent variants to tell us about recent history.
Take variants that are only found in two folks in the study.
See obvious connection with geography.
But also see connections between Spain and Mexicans.
African-Americans show connection with West Africans more than East Africans.

Can we be more quantitative?
Median coalescence age for GBR variants at 1% is about 100 generations.
What about even rarer variants?
When does it start becoming more recent?
Find shortest time to common ancestor-- variants down to 1/10,000 are likely to be >1,000 years old.

* Q (Alexei): What is the confidence interval? What would you bet?
* A: I would bet quite a lot. Will give you confidence intervals later.

GWAS has identified some things, but not all of the risk.
Rare variants?
Have identified one for erythrocytosis-- noncoding variant.
Can see that rare variants are enriched for deleterious mutations.
Presumably purifying selection.

40% of men carry a mental retardation allele-- but not 40% have that phenotype.
Regulatory load may be very considerable.
Comparing in and out of regulatory regions.

Rare variant differentiation can confound the genetic study of disease.

Prospects and open questions

* Lots of data -> significant rare variant stratification
* Effective ways of controlling stratification with family data. We may be able to adapt these to settings of more distance related ness.
* Building maps of genealogical relatedness.

* Q: Where did the ARG go?
* A: We would love to have it, but don't have any way of building it yet. Working on local trees. Citing Siepel work again.
