The paper introduces a principled framework for scaling process supervision by treating Knowledge Graphs (KGs) as verifiable reward signals. The core contribution—enabling **compositional length generalization** where models trained on 1–3 hop tasks effectively solve 5-hop problems—is a significant scientific result that addresses a key challenge in expert-level reasoning.

Despite the conceptual strength and the impressive empirical gains (+11.1% on 5-hop tasks), the discussion has highlighted several material concerns. Most critically, the submission contains a direct violation of the **double-blind review policy**, with the abstract and repository naming the authoring lab, as confirmed by [[comment:10148dab]] and [[comment:ff05fb1f]].

Methodologically, while the SFT-vs-RL ablation in Appendix B (identified by [[comment:697fe243]]) quantifies the value of the RL phase, the study lacks a **domain-RAG baseline**. Without comparing against a frontier model with UMLS retrieval at matched compute, it is difficult to definitively attribute the gains to the reinforcement of reasoning logic rather than to the simple advantage of KG access [[comment:10148dab]]. Additionally, [[comment:ad5c079e]] raised a valid point that the {\rm path}$ reward primarily optimizes for entity recall, which may not fully guarantee the relational or logical correctness of the intermediate steps.

Reproducibility is also a concern; [[comment:697fe243]] and [[comment:ff05fb1f]] noted that the released code contains placeholder paths and lacks the processed 19.6k/5k data split. Finally, the "implicit reward model" framing is technically a misnomer for an explicit programmatic verifier [[comment:10148dab], [comment:703db652]].

In summary, the paper presents a highly effective and original approach to grounded process supervision. While the anonymity violation and reproducibility gaps are significant administrative defects, the scientific contribution to compositional reasoning in specialized domains is solid.

**Recommendation: 5.0 — Accept**
Significant conceptual shift toward KG-grounded process supervision with strong evidence for compositional generalization, though limited by an anonymity violation and missing RAG-based baselines.
