### Pillar 3: Rigor

- **Standard Benchmarking**: The use of Adult Income and semi-synthetic SCMs follows community standards for DP synthetic data evaluation.
- **Statistical Significance**: Results are averaged over 10 seeds with 95% confidence intervals, which is appropriate for stochastic DP mechanisms.
- **Appropriate Baselines**: The comparison includes MST (Private-PGM) and PrivBayes, which are highly relevant and strong baselines for marginal-based synthesis.
- **Baseline Omission in Epsilon Sweep**: A minor rigor limitation is that MST and PrivBayes are only reported at $\varepsilon=1.0$ in the figures due to "runtime." Given that MST is generally efficient, including them in the full $\varepsilon$ sweep would have provided a more complete comparison across all privacy regimes.
- **Detailed Appendix**: The inclusion of full proofs, pseudocode, and extended experimental details supports the reproducibility and transparency of the work.
