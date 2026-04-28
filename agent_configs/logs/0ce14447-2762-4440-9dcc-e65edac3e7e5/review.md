# Review: Sign Lock-In: Randomly Initialized Weight Signs Persist and Bottleneck Sub-Bit Model Compression

This paper provides a rigorous and conceptually novel analysis of weight sign dynamics in deep neural networks. It identifies the "one-bit wall" as a fundamental bottleneck in sub-bit model compression and proposes "sign lock-in theory" to explain and mitigate it. The work successfully bridges optimization theory and practical compression, supported by an impressive billion-scale validation.

## Strengths
- **Conceptual Innovation**: The identification of "sign lock-in" as a mechanistic explanation for the incompressibility of learned sign patterns is a major contribution. It shifts the perspective from viewing signs as static noise to understanding them as a dynamic persistence phenomenon.
- **Theoretical Rigor**: The use of stopping-time analysis and excursions to formalize sign flips is technically sound and intuitive. Theorem 3.5 provides a principled way to study discrete events in continuous optimization.
- **Empirical Depth**: The evaluation across multiple architectures (Transformers, CNNs, MLPs) and the "billion-scale" sweep (up to 12.9B parameters) demonstrate that the lock-in effect is a robust property of modern large-scale models.
- **Actionable Interventions**: The proposed "gap initialization" and "outward-drift regularization" provide practical, lightweight methods to enhance sign stability, enabling the use of structured sign templates without sacrificing task performance.

## Weaknesses
- **Initialization Dependence**: The proposed enhancement methods are primarily training-time interventions. Their applicability to compressing already-trained models (where sign patterns are already "locked in" to random noise) is limited, though the paper's focus on "prior-based" compression is clear.
- **Baseline Scope for Compression**: While the paper demonstrates sign stabilization, a more direct wall-clock or bit-rate comparison against state-of-the-art sub-bit methods (e.g., DBF, OneBit) on standard LLM benchmarks would further strengthen the practical claims.
- **Sensitivity to Update Scale**: The boundary neighborhood radius $\epsilon$ depends on the update scale $\Delta$. For models with extremely high early-training noise or large initial learning rates, the lock-in effect may be significantly weaker than the theory predicts for the stable regime.

## Questions for the Authors
1. How does the sign lock-in effect interact with non-standard optimizers like sign-based optimizers (e.g., signSGD), where the update $\Delta$ is constant regardless of the gradient magnitude?
2. Can the "outward-drift regularization" be effectively applied during a short "refinement" phase for post-training compression, or is it strictly required during the initial phase of scratch training?
3. In the billion-scale validation, did you observe any significant differences in the re-entry ratio $g$ between early layers (e.g., embeddings) and deeper layers of the Transformer?

## Recommendation

This paper is a technically sophisticated and conceptually grounded contribution that addresses a critical gap in our understanding of model compression. It provides both a convincing explanation for a widespread empirical bottleneck and a set of practical tools to overcome it. The combination of rigorous theory and large-scale empirical validation makes this a high-quality contribution suitable for ICML.

**Recommendation: 5 — Accept**
Technically solid; high impact on sub-bit compression; excellent evaluation and clarity.
