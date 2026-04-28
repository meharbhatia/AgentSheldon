# Review: Efficient Analysis of the Distilled Neural Tangent Kernel

This paper introduces the Distilled Neural Tangent Kernel (DNTK), a novel and ambitious framework that leverages dataset distillation to address the prohibitive computational costs of NTK analysis. By identifying a fundamental "local-global gap" in the tangent space and proposing a three-stage compression pipeline, the work provides a principled method for scaling kernel-based diagnostics to larger architectures.

## Strengths
- **Conceptual Innovation**: Inverting the relationship between dataset distillation and NTK—using the former to accelerate the latter—is a brilliant paradigm shift that opens new avenues for scalable model analysis.
- **Identification of the Local-Global Gap**: The formalization of Property B (local cluster eigenspaces failing to span the global eigenspace) is a major technical contribution. It provides a rigorous explanation for why simple coreset selection is insufficient for kernel fidelity.
- **Methodological Unification**: Targeting redundancy across data, parameters, and gradient subspaces simultaneously creates a comprehensive and powerful compression framework.
- **Exceptional Visualization**: The spectral analyses in Figures 4 and 8 are highly effective at demonstrating the "coverage gap" and validating the algorithm's design.

## Weaknesses
- **The Computational Catch-22**: The method's efficiency is evaluated post-hoc, yet the initial distillation step (WMDD) requires a pretrained model and carries significant overhead. This restricts DNTK's utility to a post-hoc analysis tool for converged models, rather than a general-purpose accelerator for the training process itself.
- **The Eigen-Alignment (Inductive Bias) Gap**: DNTK's spectral optimization is label-blind. If a task requires "low-variance but high-signal" directions in the tangent space, the geometric compression will systematically discard the predictive signal. The paper relies on the empirical assumption of "Spectral Bias" without providing theoretical guarantees for predictive fidelity.
- **Local-to-Global Guarantee Gap**: Theorem 3.3 is limited to a one-step update at a fixed parameter state. There is no formal proof that a subspace optimized for local updates remains the optimal representation for global KRR generalization or uncertainty quantification.
- **Lack of End-to-End Benchmarking**: The paper lacks a "wall-clock" comparison that includes the distillation time, making it difficult to assess whether the downstream savings justify the upstream costs compared to state-of-the-art random sketching methods.

## Questions for the Authors
1. Can you provide an end-to-end wall-clock time comparison against state-of-the-art random sketching methods (e.g., Zandieh et al., 2021) that includes the time required for the initial dataset distillation?
2. How does DNTK perform on tasks where the labels are intentionally misaligned with the top principal components of the NTK (e.g., parity tasks or high-frequency signals)?
3. Given the dependency on a pretrained model, how do you envision DNTK being used during the early stages of model training for diagnostics?

## Recommendation
**Accept (Score: 7.5)**
DNTK is a high-quality, technically sophisticated contribution that successfully bridges dataset distillation and kernel methods. While the "Computational Catch-22" and the lack of end-to-end performance guarantees for downstream tasks are notable limitations, the conceptual and spectral insights are significant enough to warrant acceptance at ICML.
