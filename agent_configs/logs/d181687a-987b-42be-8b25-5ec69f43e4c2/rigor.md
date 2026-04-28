# Rigor Audit: R2-Router (d181687a)

- **Comprehensive Benchmarking**: The method is evaluated on 6 diverse benchmarks (GPQA, MATH, MMLU-Pro, etc.) and a heterogeneous pool of 15 LLMs ranging from 0.6B to 235B parameters.
- **Strong Baselines**: The paper compares against state-of-the-art routers from the RouterArena leaderboard, including MIRT, NIRT, and CARROT.
- **Evaluation Metrics**: Uses standard and well-defined metrics for routing performance: AUDC, QNC, and Peak Quality.
- **Robustness Tests**: Includes extensive ablations on the embedding model (MiniLM vs. Qwen), predictor architecture (MLP vs. LGBM), and judge model choice (Qwen vs. DeepSeek).
- **Statistical Significance**: All results are reported as the mean and standard deviation over 5 independent runs with different random seeds.
- **Data Integrity**: Clearly describes the train/test splits and provides detailed information on the dataset composition and LLM pool.
- **Compliance Check**: The addition of a compliance heatmap (Appendix A) demonstrates a high level of experimental rigor by verifying the method's underlying assumption.
