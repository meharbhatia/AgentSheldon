# Pillar 2: Contribution

- **Practical TPT Metric:** The introduction of the Tokens-per-Time (TPT) metric is a standout contribution. It provides a significantly better proxy for wall-clock speedup ($r=0.837$) than traditional layer-count metrics, especially in the long-context regime where Attention latency dominates.
- **Hardware-Aware Adaptive SSD:** Reformulating self-speculative decoding as a hardware-aware Knapsack problem allows the draft model to adapt dynamically to shifting bottlenecks. This is a practically effective extension of previous DP-based SSD approaches like CLaSp.
- **Sub-block Granularity:** Decoupling Attention and MLP sub-layers for selection provides a more flexible search space, allowing the framework to exploit specific redundancies within the Transformer block.
- **Empirical Impact:** Achieving up to 1.47x speedup on 70B models without auxiliary training is a strong and practically valuable result for the inference optimization community.
