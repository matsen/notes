---
layout: post
title:  "Ian Holmes: phylogenetic grammar and finite-state automata"
date:   2013-05-29 11:00:00
categories: MCEB2013
---

Historical perspective on grammar.
Mathematical formalism for grammar by Chomsky.
"Fruit flies like a banana" example of ambiguous parsing.
"Colorless green ideas sleep furiously"-- grammatically correct, but meaningless.

Programming languages.
Attributed grammar-- decorated parse tree.
Natural language processing uses this formalism.
Grammars for graphics-- fractals.

Grammars in molecular biology.
Stochastic regular grammars (e.g. HMMs).
Stochastic context-free grammars. e.g. for secondary structure.
Also for parsing documents.
Evolutionary grammar-- e.g. TKF model.
Reaction-diffusion models.
Turing: "stripes are easy... what about the horse?"
Cellular automata in science.
Ising model, crisals, animal patterning, spread of disease.

A grammar consists of

* a set of terminal symbols (e.g. A,C,T,U)
* a set of nonterminal symbols, including a starting symbol
* set of production rules of the form LHS -> RHS (e.g. S -> ASU)

Start with start, then repeatedly apply rules until only terminals are left.
This is a context-free grammar.
Can classify grammars in terms of the types of rules.

* Recursively enumerable (no restrictions)
* Context sensitive (can rearrange non-terminals).
* Context-free
* Regular (just adding terminals on one side)

These are all equivalent to the automata that can parse them.
Regular expression implement regular grammars.
Any algorithm can be transformed into

Grammar ambiguity.
Unambigious = only one possible parse, and on the other side are stochastic grammars (implied posterior over parses for a given sequence).

Bioinformatics grammars.

* Isochore HMMs (occasionally dishonest casino = detection of regions of uniform GC content. Gary Churchill first application to detect these.)
* Profile HMMs = statistical version of regular expression. Various, but always have some sort of linear structure.
* Genefinding HMMs: e.g. GENSCAN and Glimmer. Highly symmetric. Very complex because you are trying to implement something with context with a regular grammar.Transmembrane proteins (Krogh et al 1998).
* Pair HMMs: two output tapes (or equivalently) a single tape on which is printed a pairwise alignment. Needleman-Wunch parses a pair grammar, so does Smith-Waterman. Others: Gotoh's, DoubleScan (gene prediction using two sequences).
* RNA structure prediction: stem-loop structure. Can model subtleties of RNA folding energetics. e.g. base pair "stacking", favored loops.

RNA structure is cool.
Riboswitch structures (Barrick and Breaker, GB 2007).
Discovered by folks making them synthetically (aptamers).
http://biowiki.org/RfamRiboswitches Phosphodiester-cleaving ribozymes-- self-editing.
Hammerhead ribozymes.
RNA world?
Use them for nucleic acid logic gates.
Post-transcriptional regulation. Zipcodes - for movement of RNAs-- highly conserved. Viral

Nussinov decomposition.
Enumerates number of possible optimal folds.
Binding in middle implies a bifurcation.
Recursively remove paired bases.
Always have either a paired base or a bifurcation -> dynamic program.
Is a context free grammar.

Grammar papers by Searls make nice connections to biology.

Covariance model profiles.
RFAM database is full of these.
 * Covariance models.

Grammars in phylogenetics.
Machine learning tricks have often led to probabilistic results in bioinformatics.
Phylo-grammar: row strucutre showing the struture of the tree, and the columns showing the pairings.
Churchill and Felsenstein developed first HMM's and first phylo-HMMs!
Thorne,Goldman,Jones (1996)
Exoniphy: Siepel and Haussler, 2004.
PhastCons.
Z. Yang space-time models of autocorrelated site-to-site variation.
DLESS. Find regions that only have variation on certain branches of the tree.
Can use this to detect, e.g., elements with elevated rate on a lineage.
PFOLD (Knudsen and Hein, 1999). Phylogenetic Stochastic Free Grammar.

Recent results from Holmes group.
First, scripting complex hierarchical grammars.
XRate: tool for estimating and fitting models.
Specify functional form of models, estimate parameters, summarize/reconstruct history, and annotate missing data in the present.
Uses EM to do the fitting, so point estimates.
Problem is that EM algorithm can take a long time to

XRate screen for Drosophila ncRNAs.
Found classic ones, and lots in exons as well.
Need way to disentangling codon and folding signals (Factorial models, Jordan et al)
Common problem: highly repetitive structure.
How can we effectively script this?
XRate scheme dialect!
More repetitive models: Nielsen-Yang. See Westesson and Holmes, 2012.

XDecoder: disentangles the coding conservation signal from the RNA structure.
Find known known polio genes and known regulatory structures.
Ancestral sequence reconstruction.
An Adenovirus that only integrates into one spot in the genome.
Widely used in gene therapy.
Does the ancestral codon structure matter a lot? Turns out that not really.

ColumnRates: predicting deleterious SNPs. Does better than SIFT (Ng and Steve Henikoff) and others.
Validated on four proteins-- which have been mutated nucleotide by nucleotide.
Simple evolutionary rate estimation works better than these fancy algorithms.

Indel processes.
Alignments are nuisance variables!
We can't just take the max and think that we are going to get good parameter estimates.

Dayhoff's PAM matrix = Matrix exponential.
Felsenstein pruning recursion in vector space notation.
Can write it out as Hadamard vector product of children, and unit vector at the leaves.
Final phylogenetic likelihood is a scalar dot product.
There are some approaches to indel phylogeny, but are fairly hacky, eg. add gap character to substitution matrix.
There are full approaches, such as Bali-Phy, and work by Bouchard and Jordan.

Westesson, Lunter, Paten, and Holmes: Felsenstein with indels.
Can't realize these thing as a matrix (infinite dimensional).
Can use transducers instead. They can be multiplied (i.e. composed) or forked (feeding same input into two transducers in parallel).
Work in a sense just like Dayhoff matrices, although composition of transducers has much bigger state space than the input transducers.
Constructing evolutionary profiles for ancestral sequences.
Use banding techniques to keep time and memory at O(LN).
Can do, e.g., 90 x 7kb rhinovirus genomes.

Experiment: anything that uses ancestral alignment, even CLUSTAL, does better at inferring indel rates than fancier things that don't.
2007 paper by Lunter showing bias that comes from various types of misalignment.

* Q: What is the class of transducers that can be "exponentiated" like matrices?
* A: TKF mode is the only one with has an infintesimal generator.
* Q: Can we connect these to graphical models?
* A: HMMs yes, more complex, we can, but contrived.
