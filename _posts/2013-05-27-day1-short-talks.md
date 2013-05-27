---
layout: post
title:  Short talks Day 1
date:   2013-05-27 14:00:00
categories: MCEB2013
---


# Michael Blum (Laboratiore TIMC-IMAG): Bayesian principal component analysis to detect genomic regions involved in local adaptation
PCA in population genetics-- on 10K - 1M SNPs. From Caffali-Sforza.
Local adaptation-- greater fitness of individuals in their local habitats due to natural selection. Look for outlier regions of, say, Fst.
Local adaptation in humans driven by local pathogenic environment (Fumagalli te al PLOS Genetics 2011).
Also important in pathogens!
A PCA is an optimal approximation of rank K when we can express all data points exactly in terms of the principal components.
Bayesian version of PCA-- probabilistic model-- just add in a per-genome random term.
Location-shift model for outlier detection (Verdinelli and Wasserman 1991). Mixture model between "normal regime" and "outlier regime".
Can account for different proportions of outliers for each PC. Can get FDR.
Simulation study. Four populations. Compare to classical PCA and BaeScan (Foll and Gaggiotti 2008).
First PC has to do with ancestral divergence, PC2 has to do with local adaptation.
Get posterior on outlier probability. Nothing interesting in PC1, which is dominated by geography.
PC2 shows some selection.
Showing their method is more precise than others. Problem is harder when divergence time is long.


# Miroslav Bacak (Max Planck Inst., Leipzig): Computing medians and means of phylogenetic trees
Rooted trees with branch lengths. Add leaf at root.
Want to measure distances between trees, and medians and means of a given set of trees.
Billera, Holmes, Vogtmann (2001) tree space, called BHV tree space.
Lots of orthants pasted together representing internal branch lengths.
Take geodesic distance between points.
This space is Hadamard (= metric space of non-positive curvature).
So can take means and convex combinations by marching along geodesics.
Arithmetic mean of x_1,...x_K is the sum and divide. Can't do this in tree space.
Arithmetic mean is the unique minimizer of the sum of the squared distances (Gauss).
This function is convex, so there is a unique minimizer.
Because tree space has nonpositive curvature
Frechet mean: the unique minimizer of the squared distances.
Geometric median: just take sum of distances, rather than sum of squared distances. Also exists.

If we have a convex continuous function on tree space. How to compute a minimizer.
Proximal point algorithm: approximation sequence where we sequentially take argmin of (distance to a T_k plus a multiple of the squared distance to the previous step).
Apply this in a cyclic or random order. Can solve these one dimensional problems fine.
Q: How does this relate to consensus trees, or does it have a biological interpretation?
A: This is the mathematically nicest approach and so it's the best.
Q: Could you extend this to overlapping but not identical sets of taxa.
A: Don't know.


# Trevor Bedford (Edinburgh, soon FHCRC!): Antigenic flux in the influenza virus population
Hemagglutinin (HA) is the grappling hook, and the primary target of the immune response.
Lots of turnover.
1 in 20 sites change over the course of 10 years.
People get flu again and again. Antigenic drift means that old vaccines are useless.
We will be modeling this.
Describing hemagglutinin inhibition assay. Tells us if there is effective binding of antibodies.
Dilution tells us strength of binding.
Do lots -> different combinations of virus and antibody.
Antigenic cartography = apply multidimensional scaling (MDS) to antigenic distances.
Developing Bayesian multidimensional scaling. Model distance residuals with Normal. Take product of likelihoods.
Bayes formula.
Have BEAST sampling these.
Model position on map as a continuous character as a Brownian motion diffusion.
Phylogenetic model brings clusters together and reduces error.
Look at rate of evolution along the trunk, which goes at about 1 AG per year.
Paper is up on
Q: First dimension of MDS is time. What about second dimension?
A: It only exists transiently to show strains competing.
Q: Why doesn't a second trunk lineage exist?
A: We don't know, but perhaps strong selection
Q: Recombination?
A: Don't have to worry about it for a single segment.
Q: Convergent evolution?
A: No.


# Michael Hiller (Max Planck, Dresden): Linking phenotypic differences between species to differences in their genomes
Great variability in phenotypes.
Which genes encode this?
Mice can synthesize vitamin C. Humans cannot.
We know which mammals cannot and which can. Map to tree-- appears 4 independent losses.
Scan for genomic region that is missing in exactly those species.
Forward genetics: search for mutations that segregate with the trait.
"Forward genomics": search for regions lost.
Loss of regions for the trait may be incomplete. Reconstruct ancestral sequences to compare distances.
For vitamin C, find single region overlapping an exon, on the Gulo gene (known enzyme responsible for vitamin C synthesis).
Simulations. Method works with high specificity.
Described in a Cell paper.
Q: Why was vitamin C lost in any lineage?
A: Primates and fruit bats have lost it. Might be deleterious.


# Alain Guénoshe: Methods for consensus of partial trees
Definition of X-trees.
Leaf to leaf distances by every edge being of length one.
Majority consensus tree. Is median in tree set for Robinson-Folds distance.
Average consensus tree: (Lapointe and Cucumel 1997) calculate distances and apply NJ.
Rate of majority bipartitions
Weight of tree edge is sum of edges.
Take model tree with 16 taxa, randomly swap pairs of leaves.
Average tree does better in this case.
Only keep edges that are majority rule.
Simulation: average is good.
What to do with missing data.


# Elina Nummien: Assessing the probability of direct transmission with a branching process approach
What can we tell about transmission networks when there is lots of missing data.
Doctors studying Strep pneumo.
250 mother-infant pairs -> 300 sequences.
Can we use this to investigate transmissions?
Likelihood of a transmission tree as a function of consecutive symptom times in individuals.
If we have genotype data, can overlay that on top.
However, 40K people in the country, so there is lots of missing data.
Bayesian data augmentation.
Use genotype data to find first the possible transmission pairs, so just do the inference within clusters.
Branching process model.
Sample transmission trees starting at time of MRCA; transmissions have to happen after the time of the MRCA.
Within household epidemics -> predict how long a household will be infectious.
Then track between-household transmissions.
Can summarize to number of transmission links.
The results does depend on the cluster sizes.
