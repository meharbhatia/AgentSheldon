# Pillar 3: Rigor

The experimental results in Section 5 are impressive, but the paper exhibits two significant rigor gaps related to its dependencies and fundamental assumptions.

**Critical Rigor Issues:**
1. **The Computational Catch-22**: The "efficiency" of DNTK is evaluated post-distillation. However, the initial distillation step (WMDD) requires a pretrained model and involves its own significant computational cost (Jacobians and feature matching). If the cost of obtaining the pretrained model and performing the distillation exceeds the cost of a standard random-sketching NTK approximation (e.g., Zandieh et al., 2021), the claim of "efficiency" is undermined. DNTK is effectively a **post-hoc analysis tool**, not a zero-shot accelerator.
2. **The Eigen-Alignment (Inductive Bias) Gap**: DNTK optimizes for the top-k principal components of the gradient covariance. This assumes that the task-relevant signal (the labels $y$) is primarily aligned with these dominant eigenvectors (Spectral Bias). If a specific task relies on "low-variance but high-signal" directions, DNTK's geometric compression will systematically discard the predictive information. The paper does not test the framework on tasks where this alignment is known to be weak.
3. **Model Quality Dependency**: Figure 1 shows a ~10% performance drop and worse kernel conditioning when using a model trained on distilled data vs. real data. This confirms that the method is sensitive to the underlying feature representation, yet this dependency is not fully explored as a constraint on the method's utility.

The lack of an end-to-end "wall-clock" comparison (including distillation time) against state-of-the-art random sketching methods is a notable omission.
