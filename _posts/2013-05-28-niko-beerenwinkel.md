---
layout: post
title:  "Nico Beerenwinkel: Cancer as an evolutionary process"
date:   2013-05-28 9:00:00
categories: MCEB2013
---

Cancer is a genetic disease.
Various types of genetic alteration, including point mutations, insertions, deletions, chromosome rearrangements, mitotic recombination, loss or gain of whole chromosome arms.
Mose cancer cells are aneuploid-- genome is scrambled up.
Origin -> adenoma (benign tumor) -> carcinoma (invasive tumor).

Changes happen in specific genes.
K-ras typically an early mutation, then p16, then p53, DPC4, BRCA2.
Multistage theory. Started in the '50's by Armitage and Doll, Nordling.
This was developed before the genetic basis of cancer was found.
There was no genetic data, just by looking at incidence, seeing linear on a log-log plot.
Vogelgram-- linear genetic progression.

Hallmarks of cancer include sustained proliferative signaling, evading growth suppressors, activating invasion and metastasis, replicative immortality, inducing angiogeneisis (getting blood), resisting cell death. See Hanahan, Weinberg (2001, 2011).
Hallmarks occur in different orders.

Cancer is a very heterogeneous disease across populations, spatial, temporal, tissue, and genetic.

Cancer as an evolutionary process (Nowell, 1976).
Evolutionary tree depicting evolution of the tumor.
Ecology also acknowledged; ecosystem = tissue microenvironment.

Molecular profiling of tumors: DNA, RNA, protein, CHIP.

Caner initiation.
Small population-- will it survive?
Model using Moran process.

Oncogenes increase fitness if one allele is mutated.
Then we have an exponential waiting time for these advantageous mutations.
Many tissues with high cell turnover are ornized into small subcompartments.
Example of colonic crypts.
Mutations form polyps on outside of crypt instead of undergoing apoptosis.

Tumor suppressor genes: need two events, and the first is neutral.
Either two point mutations, or one mutation followed by a loss of heterozygosity.
"Stochastic tunneling": first mutation doesn't have to fix before second mutation occurs.
There are also mutations that cause chromosomal instability, which change mutation rate.

Now progression. Assume a fairly large population, 10^6 say. How does it become a carcinoma.
Multitype Wright-Fisher process.

    N: population size
    d: number of driver genes.
    u: mutation rate.
    s: selective advantage.

Forward simulation showing replacement by one cell type versus another.

What is waiting time to cancer?
Approximately

    \tau_k \approx \frac{k log^2[s/(ud)]}{2s \log N}

Selective advantage s is hard if not impossible to evaluate.

Bozoic et al PNAS 2010 propose a branching process model.
Passenger versus driver mutations.

Diversity of a tumor is a prognostic measure of progression to cancer.
Functional diversity is important.
Most mutations originate prior to initiation according to Tomasetti et al (PNAS 2013).

Resistance development.
Density dependent branching processes.
People are still arguing about how tumors actually progress.
We can distinguish between these using phylogenetic trees.

* Q: Immune system?
* A: Not typically modeled.

Strategies for intra-tumor sampling.

* Deconvolution of pooled sample
* Laser capture microdissection
* Cell sorting
* Single-cell analysis (single-cell genome sequencing about to come)

Phylogeny methods.
Rearragement phylogeny (Greenman et al 2011), TuMult (Letouze et al., 2010), MEDICC (Schwartz et al).
SNP array -> copy number profiles -> NJ.
Problem is that these SNPs are highly correlated.

Using bulk sequencing to estimate intra-tumor diversity.
Wright-Fisher model-- keep track of number of genotypes, not number of mutations.
High-coverage sequencing -> statistical sample of the genotypes in the tumor.
Problem of sequencing error, issue because most single nucleotide variants are expected to look at low frequencies.

Likelihood ratio test comparing clonal normal tissue to a mixed cancer population.
Beta-binomial model-- overdispersed.

Campbell group paper (Nik-Zainal et al Cell 2012): 188-fold coverage for full genome.
See four clusters.
Can look at mutually exclusive mutations -> infer evolution of one cluster to another.
Built tree by hand.

Accumulation of driver mutations: partial order of mutations to make a tumor.
How reproducible is this process? We would like to know about this partial order.
Gerstung et al, PLOS ONE 2012.
Exponential waiting times for these mutations.
Modeling using hidden conjunctive Bayesian network.
Result: poset order among genes, and on the order of pathways.
Pathways are relatively similar among cancer types.

Finding driver mutations.
Look for common ones, and for mutual exclusivity.
Additional mutations would not give additional selective advantage.
Nested structures indicative of dependency.






