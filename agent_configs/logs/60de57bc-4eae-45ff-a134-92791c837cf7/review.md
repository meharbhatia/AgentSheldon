**Strengths**
- The paper introduces a well-motivated and principled framework (PRISM) for task-specific DP synthetic data synthesis, addressing a significant limitation of task-agnostic generators.
- The three-regime categorization (Causal, Graphical, Predictive) provides a clear hierarchy of structural assumptions and their associated benefits (e.g., shift robustness vs. prediction sufficiency).
- The derivation of a closed-form budget allocation strategy directly from predictive risk bounds is a solid technical contribution that elevates the work beyond simple heuristic-based weighting.
- Extensive empirical evaluation, including both real-world data (Adult) and semi-synthetic SCMs, demonstrates the practical value of the approach, particularly in the presence of distribution shifts.

**Weaknesses**
- **Incomplete Baseline Epsilon Sweeps**: The major baselines (MST and PrivBayes) are only reported at a single privacy level ($\varepsilon=1.0$) in the main figures due to cited "runtime" constraints. This omission makes it difficult to assess how PRISM's relative advantage scales as the privacy budget becomes very tight or very loose compared to standard methods.
- **Dependency on Prior Structural Knowledge**: While Regime 3 (Predictive) handles the unknown-structure case, the paper's strongest results (Regimes 1 and 2) rely on having ground-truth causal parents or the Markov blanket. In many real-world settings, these are unknown or must be estimated privately, which would introduce additional noise not fully explored in the main experiments.
- **Limited Analysis of High-Cardinality Features**: The evaluation focuses on low-to-moderate dimensional datasets with discretized features. The scalability of the task-aware PGM fitting for high-cardinality columns remains a potential practical bottleneck.

**Questions**
1. Could the authors provide the MST and PrivBayes results for the full $\varepsilon$ sweep, or at least for the tightest budget ($\varepsilon=0.2$)? This would clarify if PRISM's gains persist or increase as noise levels rise.
2. In the "DP-learned blanket" variant mentioned in the discussion, how much of the privacy budget is typically consumed by the causal discovery step, and how does this affect the final synthesis utility compared to the Predictive regime?
3. How does the PGM fitting time scale as the size of the task-relevant subset $ increases beyond the values used in the experiments?

**Recommendation**
PRISM is a high-quality and technically sound contribution that provides a principled bridge between DP theory and practical synthetic data generation. The focus on prediction-centric utility and the formal three-regime framework are significant additions to the field. While the baseline comparisons are slightly incomplete in their privacy sweep, the overall evidence for PRISM's effectiveness is compelling.

**Recommendation: 5 — Accept**
Technically solid; high impact on prediction-centric privacy; excellent evaluation and clarity.
