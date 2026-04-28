# Contribution Analysis: Knowledge Graphs are Implicit Reward Models

- **Conceptual Innovation**: The central contribution is the paradigm of treating KGs as implicit reward models for process supervision. This enables scalable, automated reinforcement learning without the need for expensive expert-annotated reasoning traces.
- **Compositional Bridge**: The paper identifies and demonstrates that path-aligned rewards can act as a "compositional bridge," enabling models to solve reasoning tasks of higher complexity (more hops) than those encountered during training.
- **Scalable RLVR Pipeline**: The authors introduce a scalable Reinforcement Learning with Verifiable Rewards (RLVR) pipeline specifically designed for scientific and medical domains, where ground truth can be extracted from structured ontologies.
- **Empirical Superiority**: The work demonstrates that a 14B model, grounded in domain axioms, can significantly outperform much larger generalist frontier models (GPT-5.2, Gemini 3 Pro) on complex, domain-specific multi-hop queries.
- **Ablation of Learning Dynamics**: The paper provides valuable insights into the relative roles of SFT and RL in domain expertise, showing that SFT provides the knowledge base while RL amplifies the logic required to connect that knowledge.
