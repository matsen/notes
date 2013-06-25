---
layout: post
title:  "Evolution 2013: Phylogenomics"
date:   2013-06-25 08:30:00
categories: Evolution2013
---

## Mast, Austin; Buddenhagen, Christopher; Lemmon, Alan R.: Anchored Phylogenomics in the Angiosperms

Target enrichment by capture rather than PCR.
"Anchored phylogenomics": find relatively conserved regions flanked by appropriately variable regions for signal.
Some use hyperconserved elements (UCEs).
However, UCEs are rare in plants.
Lemmons paper 2012 Sys Bio to find anchoring regions.
Much better for non-model organisms.

Challenges.
Genome duplications in plants-- two whole genomes, but smaller ones and also ploidy.
No really big genome alignments for plants.

Want a tiled probe set for this "anchored" approach.
Want an expanded, genomic, version of rbcL.


## Forrestel, Elisabeth J.; Donoghue, Michael: How do measures of "signal" relate to patterns of traits distributed on a phylogenetic tree?

Blomberg's K (2003): reflects phontypic similarity in taxa relative to expectations from a brownian motion model of evolution.

    obs(MSE_o/MSE)
    --------------
    exp(MSE_o/MSE)

where `_o` means observed.
K < 1 -> close relatives resemble each other, etc.
Significance assessed by randomization of tip states.
Showing how branch lengths matter.
Lack of resolution results in inflated signal values (fix by rarefaction procedure).

Going to be thinking about discrete distributions-- can imagine that they are bimodal continuous characteristic.

Look for similar K values although distributions are different.
See subclades driving things-- want to know to what extent this happens.
Tree shape and subclade size also matters.

Take-home message-- "signal" don't man all that much.


## Cooper, Natalie; Healy, Kevin. Swofford, David: Testing irreversibility/Dollo's law using ancestral state reconstruction: How hard is it?

Funny examples-- need prior information and

"Dollo's law": complex structures, once lost, cannot re-evolve?
How do we test for this?

Originally, used maximum parsimony.
Swofford et al, showing that we need to weight different events differently-- parsimony not enough.
But how?
Can we trust parsimony reconstructions?
Example of eye pigments being lost and regained -- really?

Probabilistic methods to infer ancestral states.
Fit model, reconstruct, then test deviation (empirical Bayes).
Can also do AIC model test.
Pagel paper pioneered.

This leads to a "pipeline" for these sorts of papers.
Gunter Wagner-- paper showing digit loss and re-gained.
Wings on stick bugs.
Etc, etc.

Methodology has some issues.
Likelihood surface is very flat.
In Bayes setting, very high variance with vague priors.

Are Markov models appropriate?
How to handle root-state probabilities?
Prior belief and Bayes inference.

Test methods with simulation.
Set up a situation that is as favorable as possible for at test of Dollo's law.
Constant loss rate, Yule trees, etc.
No gains-- testing Dollo here.
How often do we see a false positive?

Example of multiple losses looking like gains.
Example where parsimony gets it wrong and ML does: issue is that the branch length not taken into account in parsimony.

Whole range of tree sizes.
ML methods correctly infer mean number of losses, but parsimony does not infer enough.
This leads to many false positive rejection of Dollo.

Model comparison methods outperform ancestral state methods.
Bayes factor comparison is better still.


## Johnson, Kevin P.: A Draft Assembly of Phylogenomic Approaches to Next-generation Genomes

"Universal primers" restrict us to non-optimal genes.
As number of taxa increase, lots of missing data.
Have to sequence same genes each time.

Targeted enrichment has some issues.

He is advocating full genome sequencing.
Would like DNA, avoid assembly and annotation.

We currently find orthologs via

* partial genome assembly and annotation (hard)
* reference based assembly (only works for closely related orgs)
* Target restricted assembly

He advocates the last one.
Do tblastn and do local assembly.
Some manual intervention needed.
Then use these sequences for analysis.
Only 3% missing data.

Automated methods needed to push through, esp intron identification.


## Lemmon, Emily; Lemmon, Alan R.: Anchored Phylogenomics: new directions and new applications

Review of their method.
They are *not* looking at UCE loci-- not enough information and issues concerning selection.

v2 vertebrate design.
Target fewer but longer loci.
> 1500bp loci.
Lots of emphasis on low amounts of missing data.

Lots of new data.
Vertebrates, arthropods, plants.

They provide service at http://anchoredphylogeny.com/
