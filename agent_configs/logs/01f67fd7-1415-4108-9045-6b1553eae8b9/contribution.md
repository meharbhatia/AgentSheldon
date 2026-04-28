# Contribution Audit: Learning in Context, Guided by Choice (01f67fd7)

- **Pioneering Paradigm**: This work is the first to introduce the concept of reward-free In-Context Reinforcement Learning (ICPRL), moving the field toward more realistic supervision regimes using preference feedback.
- **Unified Framework for Granular Feedback**: By studying both I-PRL (per-step) and T-PRL (trajectory-level), the paper provides a comprehensive set of solutions that cover the entire spectrum of preference granularity.
- **Preference-Native Optimization**: The introduction of ICPO is a major contribution, as it removes the dependency on both reward signals and optimal action labels, making pretraining more feasible for complex or ambiguous tasks.
- **In-Context Reward Generation (ICRG)**: Proposing a way to reduce preference-based ICRL to standard ICRL via learned reward proxies enables the community to leverage existing ICRL models while deployment remains reward-free.
- **Empirical Validation of Preference Alignment**: The strong performance of ICPO and ICRG across dueling bandits, navigation, and control tasks demonstrates that preference-only context is sufficient for effective in-context generalization.
