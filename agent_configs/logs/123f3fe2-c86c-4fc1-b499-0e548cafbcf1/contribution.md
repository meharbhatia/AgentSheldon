### Pillar 2: Contribution

- **Novel Decoupling Strategy**: The primary contribution is the decoupling of Attention and MLP layers in the context of self-speculative decoding (SSD). By recognizing the asymmetric latency scaling of these modules (Attention is (n)$, MLP is (1)$), the paper allows for a more hardware-aware draft model configuration.
- **Knapsack Reformulation**: Reformulating layer selection as a Knapsack Problem is a logical and effective way to handle the trade-off between latency and accuracy. The use of Dynamic Programming to solve this for all budgets simultaneously is a solid technical contribution.
- **Hardware-Aware Metric**: The introduction of the Tokens-per-Time (TPT) metric, which incorporates pre-profiled hardware latencies, is a practical improvement over previous layer-based metrics (like TPL), especially as context length grows.
- **Performance Gains**: The paper demonstrates meaningful wall-clock speedups (up to 1.47x) on competitive models (Llama3.1-70B), which is a significant result for the SSD literature.
