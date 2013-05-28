---
layout: post
title:  "Bastien Bousseau: Genome-scale phylogenomics"
date:   2013-05-28 11:15:00
categories: MCEB2013
---

Goal: understand species tree and > 20K gene trees.
Clarification between homologous genes and orthologous genes.
Typically lots of steps to get to species tree.
Today just talking about going from a gene family alignment to a species tree, with gene trees.
Idea-- if we can jointly infer lots of steps at once we can do better by integrating out uncertainty.

P(alignment, gene tree | species tree) = P(alignment| Gene tree) x P(gene tree | species tree)

Gene tree inside of species trees (Bousseau and Daubin, TREE 2010).
Duplications, duplication-loss, LGT, incomplete lineage sorting (ILS).
PHYLDOG: duplication and loss.
exODT extends PHYLDOG with LGT.

ILS methods.
Lots of them.
Rannala and Yang (Genetics 2013) model of multi-species coalescent.
Likelihood of gene tree given species tree breaks up by edges.

Now DL methods.
First parsimony: Algorithm of Zmasek and Eddy (Bioinf, 2001).
Minimize the number of DL events.
Alternative probabilistic model: Sennblad and Lagergren (SB 2009).
Ali Tofigh thesis (Lagergren) group: species tree discretization by slicing clocklike species tree, adding nodes.
Do this to add the possibility of events in the middle of edges, but can specify it by mappings to nodes.

Model of Akerborg et al, PNAS 2009: birth-death process.
Integrate out to get Pr(D,G|S).
Integrates over a large space of mappings.

Bousseau wanted to use this, but made following modifications to make things faster (Bousseau et al, Genome research 2013):

* integrate around the most parsimonious mapping
* use a double-recursive tree traversal
* integrate over a large subset of reconciliations, if not all.

P(GT | ST) = product of all of the events in the most parsimonious reconciliation.
No branch length information.

Models of gene transfer.
Identification of transfers: Nakleh et al 2005, Beiko and Hamilton 2006, etc.
Suchard (Genetics 2005): random walk through tree space model via Poisson number of SPRs.
Only for single-copy genes.

Rasmussen and Kellis (Genome research 2012) model does ILS and DL together: "DLCoal".
In practice they fix species tree and gene trees, and look for reconciliation using ILS and DL.
Locus tree pulls together different loci.

Bousseau et al model.
Dating the tree of life is difficult.
When we have fossils, can use molecular clock.
Can use transfer to date clades.
Can't have transfers back in time!

Szollosi et al (PNAS 2012) point out that we can always use extra transfers to get a transfer "back in time"
Can also root tree.
Szollosi et al (SB 2013).

Tofigh 2011 parsimony method.
Input: rooted species tree and rooted gene tree.
Output: most parsimonious DTL scenario.
Problem: NP-hard to exclude cycles.
Doyon et al (Comparative Genomics 2011) subdivide tree like before, making things much faster.
Do something clever with lineages that have disappeared, and think of population as governed by Moran process.

Rasmussen and Kellis paper (MBE 2010) use synteny information in fungi to show that gene trees are improved by using the species tree.

PHYLDOG paper.
It makes a good tree on mammalian genomes.
Assessed the quality of gene trees compared to PhyML and TreeBeST (ENSEMBL-Compara).
They evaluate methods by looking at ancestral genome sizes: better methods should yield smaller ancestral genomes.
PHYLDOG does much better.
Also look at synteny groups-- reconstruct using method by Bérard (Bioinfo 2012).

Model of gene duplication, loss, and transfer (Szollosi, PNAS 2012).
Came up with different rooting than obtained using outgroup-- they explain using long branch attraction.
Again, transfers allow dating of nodes.

Last topic-- efficient Bayesian inference of gene trees in species trees using DTL.
BeST (Liu 2007) starts from distribution of gen trees from MrBayes.
Problem is summing over all trees in a posterior distribution is time-

Amalgamated posterior probability estimation.
Use conditional clade probabilities to sum over trees.
Paper from Bret Larget (Sys Biol 2013).
If we assume that there is independence between clades that are not nested, it greatly simplifies probability calculation.
Can calculate probabilities of trees not in posterior sample-- can integrate over lots of gene trees efficiently.


