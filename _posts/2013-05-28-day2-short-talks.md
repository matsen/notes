---
layout: post
title:  Short talks Day 1
date:   2013-05-27 14:00:00
categories: MCEB2013
---


# Maria Anisminova (ETH): ML phylogeny inference with codon models

We should use codon models? They incorporate the structure of the genetic code, include synonymous substitutions, and allow us to model selection on protein.
Original motivation was detecting selection, but now scope has extended well beyond (Anismova and Kosiol, 2009 MBE).
Selection affects tree shape-- e.g. positive selection has long pendant edges. "Comb".

They developed CodonPhyML with hundreds of codon models: parametric, emperical semi-parametric.
Variants of MG, GY, and the very cool principal components models (I think of Zanetti and Zoller).
Gil, Zanetti, Zoller, Anisimova (MBE, 2013).
Get nice convergence properties for kappa, omega, and RF distance.
Includes an OpenMP version.
Model comparison using AIC.

Shows examples where codons work better and worse than AA models-- classy.
Branch supports tend to be higher using codon models.
Compare using data set using human-mouse vs. human-dog data set.
Codon model always uses wins in likelihood.
Compare with aBayes (Anisimova et al, 2011).

# Roland Swartz (EBI): MEDICC-- building trees on cancer genomes

Ovarian cancer heterogeneity.
One tree per patient.
Use Affymetrix chips to find copy numbers.
Need to deal with horizontal dependencies and overlapping events-- not IID process!

Three steps:

1. Phasing of genotype data. Implement as context free grammar, and then minimize distance using a bit of a heuristic.
2. Minimum event distance: take into account cascading events and horzontal dependencies.
    Minimum number of amplifications or deletion events.
    Implemented using finite state transducers-- start in match state, then can move into amplification or deletion events.
    Transducers give asymmetric distances, so take minimum of the two.
3. Build tree using NJ or Fitch-Margoliash.

Also can transform distance matrix to a kernel distance, and kernel PCA.
Quantify inter-tumor heterogeneity using these projections.
Use Ripley's K to quantify the local clustering.
Samples that cluster are the drug-resistant ones.


# Stephan Peischl (Bern): Accumulation of deleterious mutations in range expansions.

Mutations surfing during a range expansion (Edmonds et al 2004, PNAS).
Individuals that are near the wavefront have a small population size.
Hallatschek 2010 shows it in microbial populations.
Happens in Quebecqois by Excoffier's group.

Individual-based simulations with a stepping stone model.
Record local mean fitness, number and type of mutations.
(Peischl et al, submitted)

Take-home: deleterious mutations accumulate at the wave front, so selection is less efficient in expanding populations.
Expansion load can affect the dynamics of the expansion (!), but recovered a bit via recombination.
Also happens in 2D.
Happens for neutral mutations, advantageous, but also deleterious.

Applying to real data.
Can't do ABC because these simulations take a long time.
Interesting: there is an excess of rare deleterious mutations (e.g. Lohmuller et al 2008)
Fu et al, Keinan and Clark 2012
Peischl sees that excess is not restricted to rare variants.

* Q: Why is it not a bottleneck?
* A: Would have to be a very short and narrow bottleneck.
* Q: Why not local adaptation
* A: Not sure, but they meant to find

Genetic diversity decreases with distance from Africa.
In African populations, see 10% increase in Reduction of Heterozygosity (RH), but outside see a 5% increase.

* Q: Get different dynamics using recessive genes?
* A: These are recessive. We get similar results using dominant, overdominant.


# Amaury Lambert (Paris 6, Collège de France): Epidemics with sampling

Infer epidemic dynamics from

1. Pathogen sequence data sampled at all detection times
2. Hospital data in antibiotic-resistant epidemics stopped at the first detection times somewhere in the hospital

* Continuous time model
* Branching process assumption: excess of susceptibles
* age-dependent death rate
* constant birth rate

Transmission tree with sampling can be described by an asexual population with marks.
First imagine if there are no marks.
Plot with new transmissions always to the right.

Mathematical result: node depths H_1, H_2, H_3 form a sequence of IID RV's.
In particular, the population size N_t follows a geometric distribution
This is called a coalescent point-process, -> fast simulation of reconstructed trees, and easy computation of likelihood (product).

1. Likelihood of the tree spanned by all the distinct detection times?

Theorem (Lambert, Alexander and Stadler 2013): These pairs form a killed Markov chain with semi-explicit transitions, where the transition probability only depends on the second component.

2. Likelihood of the tree stopped at the first detection time.

(Lambert and Trapman 2013) Triples (U_i, A_i, R_i) are IID.

Proof technique: jumping contour of a tree. Jumping process characterizes the tree, and is much easier to characterize and is Markovian.


# Sarah Parks (EBI): Non-reversible models for Nt and AA models.

Reversible models are not biologically realistic, and we can't infer root.
Should be use them?
Not clear-- previous studies have been small and on nucleotides.
How do we cantify reversibility?

a. Quantify reversibility from data: estimate Qun (non-reversible) and Qgtr (reversible).
a. Use likelihood ratio test statistic for these two, and a statistic summing the absolute value of the terms of the detailed balance equations.
a. Also take difference between ML Qun and Qgtr
a. Also distance between the Qun and the closest Qgtr. (equivalent to second)

Use Pandit database, with midpoint rooting and Pandit rooting-- doesn't appear to make a difference.
38 mammals data set where the root is know.

Results on nucleotides: all measures give about the same story.
60% of data sets show significant improvement in likelihood, but trees don't change.

Results on amino acids:
There were a few that had an improvement in likelihood.

Q: Have you tried using n-mer models? CpG's are directional.
A: No.
Q: Reversibility -> can get stability issues because of complex eigenvectors.
A: Filtered out data sets for which programs failed.
Q: You have a stationarity.
A: I don't know how to


# George Scherriff (ETH) : phyloanatomy of early SIV infection

Early infection is very important.
Where does diversity come from early in infection, and where does it spread to?
Compartmentalization has been seen, but still rather little known.

Macaque data-- vaccine study.
Sampled at lymph nodes, rectal biopsy, plasma, and PBMC.
Don't have data for every tissue at every time point.
454 sequence- Gag and Tat.

Aligned to known inoculation sequence SIVmac.
Indels removed.
Corrected errors using ShoRAH diri_sampler (Zagordi et al 2011 BMC Bioinformatics), works by clustering.

Where and when does diversity arise?
In Tat, escape arises very early in lymph nodes, then spreads to other compartments.
Minimize effect of selection by only using silent sites.
Model using proportion of nucleotide and element of substitution rate.
Substitution rate much lower in tat then gag; diversity purged in tat.

High rate of migration of lymph to gut, low the other way round.
Plasma compartment relatively isolated, vs lymph, which shoots viruses all of the place.

* Q: Discordance between two and four compartment model why?
* A: Two component model is a projection of the four compartment model.
* Q: Host selection differs in various compartments? Can we separate those out?
* A: [taken offline]
* Q: PBMC only place where there is cell free virus. Does this make a difference?
* A: Not sure.
