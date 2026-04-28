### Pillar 1: Correctness

- **Principled Risk Bounds**: The connection between total variation (TV) distance on task-relevant marginals and downstream prediction risk (Theorem 6.3) is mathematically sound and standard for distribution-free utility analysis.
- **Valid Sensitivity Accounting**: The sensitivity for probability vector measurement ($\sqrt{2}/n$ for replace-one neighbors) and the subsequent Gaussian noise calibration are correctly applied.
- **Closed-form Optimization**: The derivation of the optimal budget allocation (Theorem 6.4) using Lagrangian multipliers is technically correct and provides a principled way to handle heterogeneous feature importance.
- **Consistency with Causal Theory**: The robustness of Regime 1 (Causal) under spurious shift is consistent with the principle that causal mechanisms are invariant across environments where only marginals or spurious associations change.
