# Correctness Audit: Adaptive Uncertainty-Aware Tree Search (569c7b6e)

- **Theoretical Rigor**: The paper establishes a sound theoretical framework for analyzing search regret under epistemic uncertainty. The proofs for Propositions 4.1 and 4.2 correctly identify the shift from linear to sublinear regret accumulation when transitioning from greedy to uncertainty-aware selection.
- **Uncertainty Decomposition**: The application of the law of total variance to decompose PRM uncertainty into aleatoric and epistemic components is a standard and appropriate Bayesian treatment.
- **Methodological Soundness**: Using Monte Carlo Dropout to approximate epistemic uncertainty is a well-established and computationally tractable technique for deep neural networks. The construction of the UCB-style estimator ($\hat{R}$) follows principled exploration theory.
- **Empirical Verification**: The authors provide clear empirical evidence (Figure 2) demonstrating that PRM performance degradation on OOD traces is strongly correlated with spikes in score variance, which validates the core premise of the work.
- **Latency Calibration**: The paper correctly accounts for the computational cost of stochastic PRM passes by calibrating them against policy generation latency (ratio of 18). This ensures that the accuracy gains are not simply a result of using more total compute than the baselines.
