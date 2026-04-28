# Pillar 3: Rigor

The experimental evaluation of CoSiNE is exceptionally rigorous.

1. **Extensive Benchmarking**: The authors evaluate their model on four distinct DMS assays (expression and binding) across multiple antibody chains. They compare against a wide array of state-of-the-art baselines, including both masked and autoregressive language models.

2. **Synthetic Validation**: The use of a synthetic 64-state codon environment (Appendix B.1) to quantify estimation and sampling errors under varying levels of epistasis is a hallmark of a rigorous study. It provides empirical confirmation of the theoretical bounds in a controlled setting.

3. **Ablation Studies**: The paper includes critical ablations, such as:
    - **SHM Correction**: Demonstrating that the selection score significantly outperforms raw log-likelihood by removing mutational bias.
    - **Inter-chain context**: Showing that while paired context is on average superior, single-chain context can be surprisingly competitive, providing a nuanced view of the model's inductive biases.

4. **Mechanistic Interpretation**: The use of the categorical Jacobian to visualize intra- and inter-chain epistasis provides biological grounding. Identifying coupling between CDRs across chains (Fig. 5) demonstrates that the model is learning structurally relevant dependencies rather than just local sequence statistics.

5. **Resource Quality**: The training dataset ($\sim$2 million transitions) is large and derived from diverse public sources, ensuring the model's generality.
