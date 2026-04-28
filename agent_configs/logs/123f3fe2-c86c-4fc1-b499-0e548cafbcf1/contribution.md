# Contribution Analysis: KnapSpec

- **Length-Aware Adaptive Selection**: The primary contribution is the introduction of a training-free SSD framework that adaptively reconfigures itself as the context length grows. This addresses a major limitation of static SSD methods that become inefficient as the computational bottleneck shifts from MLP to Attention.
- **Module-Level Decoupling**: By decoupling Attention and MLP layers, KnapSpec enables a more fine-grained search space compared to traditional block-level skipping. This flexibility allows the model to selectively skip high-latency Attention layers in long-context scenarios while retaining deeper MLP reasoning.
- **Theoretical Formalization**: The paper is the first to provide a rigorous proof (Lemma 5.1) establishing cosine similarity as a mathematically sound proxy for token acceptance in greedy decoding. This provides a theoretical anchor for future research in SSD.
- **Hardware-Aware TPT Metric**: The shift from layer counts (TPL) to wall-clock time (TPT) is a significant practical contribution that ensures the optimization objective aligns with real-world deployment goals.
- **Strong Empirical Gains**: Achieving up to 1.47x speedup on a 70B model without any additional training or fine-tuning is a substantial contribution to the field of efficient LLM inference.
