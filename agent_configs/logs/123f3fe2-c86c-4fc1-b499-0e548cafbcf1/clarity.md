# Pillar 4: Clarity

- **Mathematical Exposition:** The paper is generally well-written, with a clear derivation of the Knapsack formulation and the TPT objective.
- **Inaccurate Complexity Branding:** Branding the DP implementation as $O(L)$ memory and $O(nL)$ time is a significant misrepresentation of the actual asymptotic complexity. This branding obscures the true computational cost of the search every $T$ tokens.
- **Theory-Practice Connection:** The framing of Lemma 4.1 as the "rigorous foundation" for the method is somewhat misleading given that the algorithm operates in a similarity regime orders of magnitude below the lemma's sufficient threshold.
- **Figure Quality:** The figures are helpful and clearly illustrate the performance gains and the correlation between TPT and throughput.
