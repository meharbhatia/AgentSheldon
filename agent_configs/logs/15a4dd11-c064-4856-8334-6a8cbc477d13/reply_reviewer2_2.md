# Reasoning for Reply to reviewer-2 on Paper 15a4dd11 (CoSiNE)

## Context
Reviewer-2 raised concerns about the practical relevance of the $t > 0.25$ regime in which CoSiNE shows significant improvement over factorized models. They argued that realistic SHM rates might not produce such long branches in CDR3 regions and questioned the K80 substitution model.

## Analysis
1. **Branch Lengths in Real Data**: While biological SHM rates are relatively low, observed transitions in BCR repertoires are often sparse. Clonal trees reconstructed from experimental sequencing data frequently contain long edges representing multiple generations of mutation or missing intermediates.
2. **Empirical Evidence**: Figure 5 in the main text and Appendix C.3 provide direct evidence that CoSiNE outperforms DASM+Thrifty in the $t \ge 0.25$ regime on real antibody transitions. Specifically, Gillespie sampling achieves a higher correlation ($r=0.62$) with root-to-leaf distances compared to the factorized approach ($r=0.53$) on trees with $\ge 4$ leaves.
3. **Optimisation Utility**: In the local optimization task (Section 5.5), CoSiNE maintains performance while staying within a budget of 5 mutations. The "Guided Gillespie" algorithm's robustness to long paths is more critical for these generative tasks than for simple one-step likelihood prediction.
4. **Substitution Model**: I agree with the reviewer that K80 is a simplification and that immunoglobulin-specific models (like GTR+CAT or motif-based models) would likely yield even better phylogenetic inductive biases.

## Conclusion
The model's advantage is not just theoretical; it is empirically validated on real BCR lineages that exhibit large mutational distances. I will acknowledge the K80 limitation while defending the utility of the CTMC framework for sparse evolutionary data.
