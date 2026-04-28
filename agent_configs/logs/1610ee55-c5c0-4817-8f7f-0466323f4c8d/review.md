# Review: Knowledge Graphs are Implicit Reward Models: Path-Derived Signals Enable Compositional Reasoning

This paper proposes a novel post-training pipeline that uses Knowledge Graphs (KGs) as implicit reward models to teach LLMs compositional multi-hop reasoning. By rewarding the alignment between a model's reasoning trace and ground-truth KG paths, the authors demonstrate significant gains in zero-shot generalization to complex medical queries.

## Strengths
- **Principled Paradigm Shift**: The core idea of using KGs for automated, verifiable process supervision is a significant conceptual contribution. It provides a scalable alternative to expensive human-in-the-loop annotations.
- **Evidence of Compositional Generalization**: The model's ability to generalize from 1-3 hop training to 4-5 hop reasoning tasks (unseen during training) is a powerful validation of the "compositional bridge" enabled by path-aligned rewards.
- **Superior Domain Expertise**: A 14B model outperforming GPT-5.2 and Gemini 3 Pro on complex multi-hop medical tasks is an impressive result, demonstrating that grounded, specialized training can surpass generalist scale.
- **Empirical Rigor**: The work is supported by extensive ablations, stress tests against format perturbations, and detailed stratification by difficulty and clinical category.
- **Clarity and Transparency**: The manuscript is exceptionally well-written and provides comprehensive details on data construction, training hyperparameters, and reward formulation.

## Weaknesses
- **KG Dependency and Robustness**: The framework's performance is likely sensitive to the quality, completeness, and noise level of the underlying KG. The paper would be strengthened by an analysis of how sparse or incorrect KG facts affect the learning signal.
- **Entity Extraction Heuristics**: The {path}$ reward relies on token-level intersection between the reasoning trace and path entities. This approach may be sensitive to variations in terminology or paraphrasing, which are common in clinical domains.
- **Instability of Baseline RL**: The authors noted that RL without a prior SFT phase (Zero-RL) was unstable or ineffective. More detailed discussion on the failure modes of Zero-RL (e.g., linguistic collapse or reward hacking) would provide valuable guidance for the community.

## Questions for the Authors
1. How does the path alignment reward handle synonyms or semantically similar clinical terms that are not exact token matches with the KG?
2. Did you observe any specific types of "reward hacking" when using the path-alignment signal, and how did the repetition penalty address them?
3. How would the performance change if the KG was intentionally made sparse or noisy (e.g., by removing 20% of edges)?

## Recommendation

This is an excellent paper that provides a clear, scalable, and effective path toward enabling compositional reasoning in specialized domains. The conceptual innovation of using KGs as implicit reward models is well-supported by both theoretical framing and strong empirical results. The work is highly relevant to the ICML community and represents a significant step forward in the study of grounded LLM reasoning.

**Recommendation: 5 — Accept**
Technically solid; high impact on the field of compositional reasoning and domain-specific LLMs; excellent empirical support and clarity.
