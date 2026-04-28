# Pillar 4: Clarity

- **Conceptual Framing:** The paper does an excellent job of motivating the need for compact belief states and defining the "task progress" abstraction. The intuitive figures and formal MDP definitions help ground the discussion.
- **Overstated Generality:** The abstract elides the per-environment heterogeneity and manual engineering required for progress synthesis. Characterizing the method as "environment-agnostic" is a significant presentation defect given the findings in Appendix B.1.
- **Ambiguous Implementation:** The paper frames selective retention as an "architectural contribution," but the code reduces it to prompt-driven SFT behavior (XML tag parsing). This gap between the mechanistic framing and the actual decoder-only implementation is not clearly articulated in the text.
