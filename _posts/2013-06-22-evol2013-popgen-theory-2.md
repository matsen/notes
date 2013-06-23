---
layout: post
title:  "Evolution 2013: Population genetics theory II"
date:   2013-06-22 10:30:00
categories: Evolution2013
---

## Spencer, Hamish; Priest, Nicholas: The Modification of Dominance in Response to Sexually Antagonistic Selection

Sexually antagonistic selection = Conflict is when fitness of an allele depends on sex.

Evolution of dominance.
Fisher argued that wild-type alleles should evolve to be dominant,
Wright countered that selection is weak-- only applies to
Otto and Brouquet found settings when evolution of dominance can happen.

Spencer proposes a modifier locus at a modifier locus.
A bit of a complicated story depending on parameter regimes.
Sexually antagonistic selection can maintain sufficient genetic variaiton to allow for the evolution of dominance modifiers.


## Furrow, Robert; Feldman, Marcus W: Epigenetic variation and the response to selection.

How does epigenetic variation change with respect selection.
In particular, it's less faithful.

Example of methylation.
C elegans, arabadopsis, agudi locus.

How do epiallele frequencies change across multiple generations.
Very simple model-- two states, infinite population.
Write down recursion-- same as usual one.
Assume small s -> expansion.
Basically we are thinking about really high mutation rates.

If we start at mutation balance.
This high mutation rate discounts the effect of selection at every step.
Can derive equilibrium state.

There might be a lot of diversity in epimutation state, but that could just be reflective of high mutation rates.


## ALCALA, Nicolas; JENSEN, Jeffrey D.; VUILLEUMIER, Séverine: The Signature of Past Population Isolation on Gene Genealogies and DNA sequence data

Intro.
Examples of Drosophjila, human-neadertal, viral populations.

Model I: isolation scenario continues.
Model II: isolation scenario only in the past.
Going to use TMRCA and site-frequency spectrum.
D populations with migration.
t_w = within deme.
t_b = between deme.

What you would expect for model I.
For model II: multiple modes and large variance. Also makes sense.
-> trees with some short and some long branches, without many middling ones.

Skyline plots falsely detect successive changes of effective population size under model II.
Can find isolation period is it wasn't too long ago and if isolation stronger.

Now site frequency spectrum, both within a local SFS (one population at a time) and pooled. Also correlations between demes.
It's difficult to disentangle from other processes using only local SFS.
Better using pooled.
Complex dynamics for correlations, definitely more informative.


## Coop, Graham; Berg, Jeremy:	The coalescent with soft sweeps

Classic sweep model: Maynard-Smith and Haigh (1974).
Low diversity around selected site, but recombination brings back that diversity.

Violations of this model.
Selection on standing variation: change of environment leads to a change of selective pressure on polymorphic allele.
Example of sticklebacks and domestication.

Model for these.
Drifting allele, then change of environment.
Arose on a single haplotype, but can have recombined onto logs of different haplotype background.
A few of these different backgrounds.

Look at coalescent ancestry.
"Neutral phase" versus "selected phase" (short).
At selected sites, can approximate by coalescent rate of 1/(Nf), f is the frequency.
Can be much faster than 1/N, which is rate when

Properties of selection on the standing variation are determined by the properties of the coalescent tree atht eselected site.
He can derive recovery of diversity as we move away from from selected sites.

What about distribution of haplotypes?
Enough to know frequency of recombination rates.
Infinitely many alleles -> Ewens sampling formula.


## Jewett, Ethan; Rosenberg, Noah: Using deterministic functions to approximate coalescent distributions

Sample n_0 alleles from present day.
Going back in time, can obtain many obtain many colescent formulas by conditioning on n_t.

Difficulties.
Tough to compute when large population size.
Numerical stability.

JAFS - joint allele frequency spectrum.

Forward time diffusion approximation: Gutenkunst &c 2009.
Asymptotic approximation by Griffiths 1984.
Assume n_t is equal to its expectation by Slatkin 2000.
This is reasonable!
He shows that n_t is almost deterministic in some example. (as example, cites Frost and Volz 2009)

Much faster of course!

Today: when is this approximation accurate?
It is asymptotically accurate, they also have asymptotic error estimate.

Deterministic approximation is more accurate (in some regimes) than the Griffiths approximation.

Deterministic approximation is much faster than complete and Griffiths.

