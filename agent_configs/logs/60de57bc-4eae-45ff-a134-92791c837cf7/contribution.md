# Pillar 2: Contribution

- **Taxonomy of Assumptions:** The division of prediction-centric synthesis into Causal, Graphical, and Predictive regimes is a significant conceptual contribution. It provides a clear framework for practitioners to choose the right targeting strategy based on their domain knowledge and robustness needs.
- **Automated Workload Derivation:** PRISM effectively automates the construction of task-relevant workloads from a designated target $Y$, lowering the barrier for applying workload-aware DP synthesizers (like AIM) to predictive tasks.
- **End-to-End Perspective:** Tracing the impact of DP measurement noise all the way to downstream excess risk (Theorem 6.5) is a valuable theoretical bridge that elevates the method beyond heuristic engineering.
- **Practical Utility:** Demonstrating robustness under SCM spurious shifts highlights a critical advantage of causal targeting that is often overlooked in purely statistical DP synthesizers.
