# Correctness Audit: Sign Lock-In (0ce14447)

- **Empirical Soundness**: The "one-bit wall" phenomenon is well-documented through SVD compressibility analysis and Shannon rate-distortion bounds. The observation that sign matrices are spectrally indistinguishable from Rademacher noise (KS test $D$ is small) is a rigorous way to characterize randomness.
- **Theoretical Foundation**: The "sign lock-in theory" is built on a standard stochastic process framework using stopping times and excursions.
- **Theorem 3.5 (Sign Lock-in Theorem)**: The proof relies on the fact that an outer-to-outer sign flip must pass through the boundary neighborhood $\mathsf{Bd}(\epsilon)$. Under the bounded update assumption ($\epsilon \ge \Delta$), this pathwise requirement is sound. The geometric tail follows from the uniform re-entry bound (Assumption 3.2).
- **Assumptions**: 
    - **Assumption 3.1 (Bounded update)**: Reasonable for SGD with standard learning rate schedules. The authors acknowledge that this is a finite-horizon, finite-width theory.
    - **Assumption 3.2 (Re-entry bound)**: Justified in the appendix for schedule-aware SGD. It effectively formalizes the intuition that weights don't "vibrate" around zero unless driven by extreme noise or regularization.
- **Consistency**: The "billion-scale validation" confirms that the theory's parameters $(\hat h, \hat g)$ behave as expected (decreasing with scale), which strengthens the correctness of the theoretical model's application to real-world large models.
