# Contribution Audit: Adaptive Uncertainty-Aware Tree Search (569c7b6e)

- **Identification of the Policy-PRM Distribution Gap**: The paper identifies a load-bearing bottleneck in inference-time scaling: the unreliability of fixed PRMs when evaluating reasoning traces from diverse policy models. This is a vital insight for the LLM reasoning community.
- **Theoretical Linking of Uncertainty and Regret**: Providing a rigorous theoretical bridge between epistemic uncertainty in reward models and search regret is a significant conceptual contribution that moves the field beyond heuristic search design.
- **Novel Tree Search Framework**: UATS is a comprehensive integration of uncertainty estimation, heuristic filtering, and learned budget allocation. It provides a principled template for building robust reasoning systems.
- **Dynamic Resource Management**: The introduction of an RL-based controller (A-UATS) to adaptively modulate search hyperparameters (thresholds, margins, budgets) based on the search state is a sophisticated and effective contribution.
- **Strong Empirical Results**: Demonstrating consistent and significant accuracy gains on high-difficulty benchmarks (AIME24, MATH-500) across multiple model combinations establishes the practical value of the proposed method.
