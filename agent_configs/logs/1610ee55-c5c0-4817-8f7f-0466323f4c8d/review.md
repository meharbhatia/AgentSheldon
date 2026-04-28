**Strengths**

- **Principled Paradigm Shift:** The core idea of using Knowledge Graphs (KGs) for automated, verifiable process supervision is a significant conceptual contribution. It provides a scalable alternative to expensive human-in-the-loop annotations for scientific reasoning.
- **Evidence of Compositional Generalization:** The model's ability to generalize from 1-3 hop training to 4-5 hop reasoning tasks (unseen during training) is a powerful validation of the "compositional bridge" enabled by path-aligned rewards.
- **Specialized Scale Advantage:** SHOWING that a 14B grounded model can outperform much larger frontier systems like GPT-5.2 and Gemini 3 Pro on specialized tasks demonstrates the high utility of domain-specific post-training.
- **High Technical Specification:** The manuscript provides commendable detail on most reward constants and training hyperparameters, allowing for a high degree of transparency.

**Weaknesses**

- **Reward Soundness Concerns:** The $R_{\rm path}$ reward relies on token-level intersection with path entities without verifying relational logic or step order. This heuristic could reward "keyword recall" rather than true logical composition.
- **Incomplete Baseline Scope:** The evaluation lacks a **domain-RAG baseline** (e.g., frontier model + UMLS retrieval). Without this, it is difficult to isolate whether the 5-hop gains are driven by the reinforcement of reasoning logic or simply by the model's access to structured KG facts.
- **Double-Blind Policy Violation:** The abstract and linked repository explicitly name the authoring lab ("jha-lab"), which is a direct violation of double-blind review requirements.
- **Reproducibility Gaps:** The absence of the processed 19.6k/5k data split and serialized KG paths in the public repository hinders independent verification of the 14B results.
- **Weak Option-Shuffling Test:** Randomizing only distractor order while keeping the correct label constant is an insufficient probe for positional bias in MCQs.

**Questions**

1. Can the authors provide results for a domain-RAG baseline to isolate the marginal benefit of RL-based reasoning reinforcement over simple KG retrieval?
2. How does the path alignment reward handle cases where a model uses valid medical knowledge that is correct but not present in the specific UMLS triples?
3. Could the authors clarify the definitions of $\phi_{\rm rep}$ and the scale-vs-clip order in the reward formulation?

**Recommendation: 4 — Weak Accept**

The use of KGs for process supervision is a principled and effective idea with strong empirical support for compositional generalization, but the study lacks a domain-RAG baseline to isolate the RL contribution and contains a direct violation of the double-blind policy.
