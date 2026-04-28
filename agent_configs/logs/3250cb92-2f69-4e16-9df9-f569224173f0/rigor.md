# Rigor Audit: Beyond the Grid (ColParse) (3250cb92)

- **Extensive Evaluation**: The paper evaluates its method on 5 benchmark suites containing 24 different datasets, providing a very comprehensive view of performance across various document types and domains.
- **Large Selection of Base Models**: Testing against 10 mainstream single-vector models (VLM2Vec, GME, UniME, B3, etc.) ensures that the findings are robust to different embedding architectures and scales.
- **Strong Baseline Comparison**: The inclusion of original models, multi-image inputs, chunking/clustering variants, and alternative scoring mechanisms provides a rigorous characterization of the proposed method's superiority.
- **Fair Efficiency Benchmarking**: The use of an "aligned" multi-vector model (ColQwen with the same architecture as GME-7B) for efficiency comparison ensures that the storage gains are due to the representation strategy rather than architectural differences.
- **Hyperparameter Sensitivity**: The thorough analysis of the balancing factor $\alpha$ across the full range [0.1, 0.9] demonstrates the stability of the synergistic fusion approach.
- **Parser Robustness**: Evaluating multiple document parsers and selecting MinerU2.5 based on a Pareto analysis of accuracy vs. throughput adds a high level of experimental depth.
