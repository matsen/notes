---
layout: post
title: "Naruya Saitou: Evolutionary patterns of conserved non-coding regions"
date: 2013-07-05 12:30:00
categories: ad-hoc
---


He says it's year 0013. Says "we scientists should avoid Jesus Christ", and so there is no reason to use a Christian calendar.

Has recently re-started C programming and is starting phylogeny algorithms development again!
Is working on software to reconstruct trees on one million leaves.

MISHIMA2 has recently been developed by Kryukov.
He has an upcoming Springer book "Introduction to Evolutionary Genomics."

**First story**: [Matsunami and Saitou, Vertebrate Paralogous Conserved Noncoding Sequences May Be Related to Gene Expressions in Brain](http://gbe.oxfordjournals.org/content/5/1/140.short)

Conserve non-coding sequences (CNSs).
Examples of CNSs: canditate cis-regulatory elements.
CNS found in HOX cluster-- JME.
Paralogous coding and non-coding segments.
Candidates for followup.

Ohno-- book "Evolution by Gene Duplication"
He was the one who proposed "junk DNA" term.
Very nice Japanese put-down of ENCODE results-- "if we don't see evolutionary conservation then I don't think that we can assign function."

Methods:

* detection of orthologous synteny blocks
* detection of paralogous synteny blocks
* detection of orthologous CNS
* detection of paralogous CNS

Di, Tri, and Tetra- block definition of orthologous genes. Some genes can be missing.
Once they find these, they perform blast to find paralogous CNS-harboring genes.
Fewer pairs of CNS than protein-coding ones.
They find many transcription factor binding sites.
Example of regulation near FOXP1/2.

Look at GO annotation enrichment.
Also, two-fold increase of CNS in brain.


**Story 2**: [Takahashi and Saitou, Identification and Characterization of Lineage-Specific Highly Conserved Noncoding Sequences in Mammalian Genomes](http://gbe.oxfordjournals.org/content/4/5/641.short)

Compare primates and rodents.
Where are some lineage-specific conservation of non-coding sequence.
Motivated by similarity on the protein level, but clear phenotypic differences.

In some cases, see very high conservation very close to identified CNS.
4-5% of our genome.
Compare to human SNP- HapMap.
Higher conservation than SNPs.
They are more abundant in intronic regions rather than intergenic regions.

Then compare orthologs-- skipped though.
See some genes that have both ultra conserved elements and primate-specific CNS.
These are statistically significantly enriched.

**Story 3**: Babarinde (from Nigeria) and Saitou.
Expand this work to carnivores and cetartiodactyl lineagaes.

Under revision at GBE, so I'm not going to take notes.

**Story 4**: Hettiarachici and Saitou. Plants.

Not submitted, so I'm not going to take notes.
But whoa, pretty neat differences between mono- and dicots, as well as grasses.

* Q: Is the plant signal just SINEs or RNA genes?
* A: No.
* Q: Is change of spacing just what you would expect from random changes.
* A: Interesting question, but we don't have great genomes.
* Q: Chimps versus humans?
* A: Chimps are too close to human. Chimp genome not very good-- 6x.


**Post talk meeting**: was fun.
He definitely thinks that NJ is the best way to reconstruct tree topologies, although ML has its role as a way to optimize branch lengths (!).
I pried him about this, but he didn't seem to have any clear reason other than computational efficiency.
