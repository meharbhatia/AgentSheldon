# Review: Learning in Context, Guided by Choice: A Reward-Free Paradigm for Reinforcement Learning with Transformers

This paper introduces the first comprehensive framework for reward-free In-Context Reinforcement Learning (ICRL), leveraging preference feedback as a more practical and robust supervision signal. By proposing specific algorithmic solutions for both immediate (step-wise) and trajectory-level preferences, the authors successfully demonstrate that transformer-based policies can infer task structure and generalize to new tasks in context without explicit reward signals or optimal action labels. The work is supported by sound theoretical derivations and strong empirical results across diverse task modalities.

## Strengths
- **Conceptual Significance**: This is a pioneering work that expands the scope of ICRL to include preference-based alignment. It identifies and addresses a major practical limitation of current ICRL methods—their reliance on explicit, semantically consistent reward functions across tasks.
- **Versatile and Unified Framework**: The paper elegantly handles both fine-grained (I-PRL) and coarse-grained (T-PRL) feedback. The introduction of In-Context Preference Optimization (ICPO) is particularly noteworthy for its ability to learn directly from preferences without relying on costly optimal action labels during pretraining.
- **Strong Empirical Results**: The finding that preference-based methods can achieve performance comparable to, or even better than (in the case of ICPO on Meta-World), reward-supervised baselines is a powerful result. It highlights the potential of preference signals for complex, high-dimensional continuous control tasks.
- **Theoretical and Methodological Rigor**: The derivation of the ICPO objective from first principles and the logical reduction of T-PRL to a standard ICRL problem through learned reward proxies demonstrate a high level of technical soundness.

## Weaknesses
- **Feedback Granularity Sensitivity**: As evidenced by the results, there is a significant performance gap between I-PRL and T-PRL. While this is fundamentally expected due to the sparsity of trajectory-level preferences, the paper could provide more insight into the limits of in-context adaptation from weak feedback alone.
- **Task-Dependent Hyperparameters**: The observation that the hyperparameter $\lambda$ in the ICPO objective has opposite optimal behaviors in DarkRoom versus Meta-World suggests that the formulation is sensitive to the nature of the task (discrete vs. continuous). This task-dependency slightly complicates the claim of a fully unified framework.
- **Scalability to Long Horizons**: The ICRG method's reliance on learning a dense reward representation from a single trajectory-level preference label is likely to face significant credit assignment challenges as the horizon $H$ increases. A more thorough sensitivity analysis with respect to trajectory length would be beneficial.

## Questions for the Authors
1. In the T-PRL setting, how does the performance of the reward estimator and the downstream policy scale as the horizon $H$ increases? Is there a point where the trajectory-level preference becomes too uninformative for effective in-context adaptation?
2. Why does ICPO outperform DPT in the Meta-World environment? Do you believe the preference signal provides a smoother or more robust gradient for continuous action spaces compared to the supervised cross-entropy loss on potentially noisy optimal action labels?
3. Have you considered a symmetric version of the ICPO objective that balances the likelihood of preferred and non-preferred actions without requiring the $\lambda$ hyperparameter to be manually tuned for different task types?

## Recommendation

This paper is a high-quality, conceptually original, and technically solid contribution to the field of In-Context Reinforcement Learning. It addresses a fundamental practical challenge with a principled set of solutions and provides convincing empirical evidence of their effectiveness. The work is likely to open up new research directions in reward-free meta-learning and preference-based alignment for foundation models in RL.

**Recommendation: 5 — Accept**
Technically solid; high impact on the sub-field of ICRL; excellent evaluation and clarity.
