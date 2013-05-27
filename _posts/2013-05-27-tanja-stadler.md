---
layout: post
title:  "Tanja Stadler: Phylogenetics in action"
date:   2013-05-27 12:28:14
categories: MCEB2013
---

### Tanja Stadler: Phylogenetics in action-- merging epidemiology and evolutionary biology

Joint work with Sebastien Bonhoeffer, Gabrel Leventhal, Denise Kühnert, and Alexei Drummond.

Epidemiology classically uses incidence data, and fit SIR model

Limitations:

* what happens if sampling in the early epidemic was missed
* how to integrate data in two neighboring countries?

Use genetic data, and phylogeny as proxy for infection network.
Example: HIV zoonotic transmission dating.
Now people are looking at transmission process-- phylodynamics.
Citing H1N1 work of Fraser at al, 2009.

We'd like to merge phylogenetics and epidemiological model.
How?
General framework:
Summarize tree model parameter with eta, and evolutionary model parameters with theta.
So sequence distribution determined by both eta and theta.

* Q: Are you only looking at binary trees?
* A: Yes. It's realistic when we are looking at timed trees.
* Q: One host, one sequence?
* A: Yes. Not considering within-host evolution. Consensus sequences. If thinking about both, it's similar to a gene-tree species-tree (Alexei may be talking about this).

Take Bayesian approach for estimating epidemiological parameters.
Don't really care about phylogenetic resolution, happy to average over them.
Bayes theorem.

                           f(data|T,theta) f(T|eta) f(eta,theta)
    f(T,eta,theta|data) =  -------------------------------------
                                           f(data)

* f(data|T,theta): sequence evolution model, Felsenstein. Neutral evolution of sequences.
* f(T|eta): no extra hidden parameters like population sizes.
* f(eta,theta): prior

Note: sequence evolution is independent of eta, corresponding to a neutral model.
Use MCMC to integrate. Peter Arndt wants details about how that works.

Would like to use present day data to infer past processes.

* Coalescent model (Drummond et al Genetics 2002)
* Birth-death model (Stadler et al MBE 2012)

Epidemiological changes over time

* (Drummond et al MBE, 2005)
* (Stadler et al PNAS 2013)

SIR model dynamics

* Coalescent model (Kühnert et al)
* Birth-death model (Leventhal et al.)

Host population structure

* Coalescent model (Volz Genetics 2012)
* Birth-death model (Stadler and Bonhoeffer Phil Trans Royal Soc B 2013)

Review of coalescent.
Images from Kühnert et al (Int. Gen. Evol., 2011).
Constant population size leads to long branches, and exponential leads to unbalanced trees with a combination of long and short edges.
Kingman coalescent when sampling all at once.
Drummond et al (Genetics 2002) showed how to calculate likelihood with sequentially sampled sequences.
Population size is always number of infected individuals.

Example of Hepatitis C, work of Oliver Pybus (Science, 2001).
How can we determine basic reproduction number R_0?
40-100 sequences per sub type.
Fit exponential growth coalescent and obtain growth rate r (i.e. eta = r)
Using SIS model, R_0 = rD+1 (where D is expected time of infectiousness)
Showed that different subtypes have different R_0's.

We need to relax the idea of a constant growth rate.
-> Bayesian skyline plot. (Drummond et al, MBE 2005)
Piecewise-constant population size. (Like the skyline of New York)

* Q: Identifiability? Can refine the skyline plot...
* A: The number of change-points is pre-specified.

Egypt HCV example. Much higher prevalence than surrounding countries. When did high prevalence emerge, and why?
Look at skyline plot. See a big jump in the 1930's.

Limitations of the classic coalescent.
Coalescent rates only depend on the number of infected, i.e. it is of the form lambda_0 I, (I is number of infected).
What we really want is lambda_0 S/N, so the overall rate: lambda_0 I S/N.
Example of simulated data where the generalized skyline gives too late of a coalescent. (Volz et al Genetics, 2009)

* Q: Why does skyline break down in this setting?
* A: Not really sure.
* Q: What about biased sampling? Would be nice to include that.
* A: Not clear to incorporate that in the coalescent.
* Q: What is basis for saying that skyline plot is not working? Just simulation?
* A: Two things. First, we would like a fully parametrized SIR model. Second, we want to get closer to an individual-based method.

Mentioning the Volz work on host population structure.

Now shifting to her work.
Birth-death model for transmission.
SIR. Resistance = "death" in BD model. Also have a sampling probability.
Parameters may depend on time, # suceptibles, type of infected individual, or they may be constant.
Idea is there are lots more lineages than actually get sampled.
Challenge: how to calculate likelihood of phylogenetic tree using all of these parameters?
Rather than using coalescent in BEAST, use a BD model.

Epidemic outbreaks.
First rather than having a full SIR, just look at infected number.
Use master equations
define p(t) as the probability density that an given individual at time t produces the observed descending tree.
t_{or) = time of origin
p_0(t) probability density that a given individual at time t has no sampled descendants.
Master equation is a forward time differential equation describing growth of p(t).
Can solve this and then write out the likelihood of an observed tree.
Stadler JTB 2012.
Simulate epidemic outbreak. Get correct lambda - delta in 95% confidence interval 97% of the time.
Coalescent only gets it right 55% of the time.
When does it get it wrong?
The problem is not violation of small sample size from a large population.
It's the deterministic population size. Lots of stochasicity in early events.
Now simulate under the coalescent, and then reconstruct using BD. Both methods work well.

Now parameter changes through time.
Piecewise constant version of before.
Stadler, Kühnert et al (PNAS 2013) application to HCV example.
Bump in R_0 in the first half of century. Public health history shows a large TB vaccination project at that time.

SIR model (submitted by Kühnert). Approximation that does not implement exact SIR dynamics.
Leventhal work gets exact likelihood. Not clear yet how much it matters.
Coalescent model implemented in BEAST.
BDSIR add-on to BEAST v2.0
expoTree (R package by Leventhal).

Host population structure.
Say IV drug users versus sexual transmission.
Now trees have colored tips.
Can we classify people into spreaders versus super-spreaders?
10% super-spreaders, but super-spreaders spread 10x more effectively than
Covered in Stadler and Bonhoeffer (Phil Trans Royal Soc B 2013)

* Q: For super-spreaders, can you infer who is who?
* A: We have only an ML model so far, and don't have enough sampling density to get high confidence estimates.
* Q: How do you evaluate goodness of fit of models?
* A: LRT for super spreader versus non, but nothing in general.
