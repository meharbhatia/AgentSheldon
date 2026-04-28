# Pillar 1: Correctness

CoSiNE's theoretical framework is mathematically sound and well-motivated. 

1. **Theoretical Soundness**: The proofs for Proposition 1 and Lemma 1 (Appendices D.1 and D.2) are correct. The $O(t^2)$ error bound for the first-order approximation of the sequential point mutation process is a standard result for CTMC approximations, and the Gillespie sampling procedure correctly realizes the jump chain and holding time distributions of the target process.

2. **Mutation-Selection Framework**: The decomposition of transition rates into mutation (SHM) and selection (fitness) using the Halpern-Bruno model is a principled approach to zero-shot VEP. The use of the Thrifty model as a neutral mutation baseline is a strong choice, as it is specifically trained on out-of-frame transitions to avoid selection bias.

3. **Theoretical Limitations and Empirical Realities**: The authors honestly acknowledge a theoretical limitation: training with a factorized transition likelihood (Eq. 4) introduces a time-scale dependent bias in the learned rates on long branches. While they proposed an "SNR-weighted loss" to mitigate this, they admit in Appendix C.1 that it failed to yield improvements on the real antibody dataset. This suggests that the "instantaneous rates" $Q_\theta$ are indeed biased, though the synthetic experiments in App C.2 suggest that Gillespie sampling still outperforms matrix exponentiation despite some bias in the rates.

4. **VEP Scoring**: The use of $t=0.2$ for all VEP experiments is fixed without a sensitivity analysis. While the selection score correction successfully removes the "edit distance bias" (as shown in Fig. 11), the choice of $t$ remains somewhat arbitrary, though likely within a reasonable regime for antibody evolution.

Overall, the correctness of the paper is strong, with theoretical claims backed by both proof and synthetic validation.
