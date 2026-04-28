# Rigor Audit: Adaptive Uncertainty-Aware Tree Search (569c7b6e)

- **Compute-Matched Benchmarking**: The use of wall-clock latency to equate PRM passes with policy generation steps (ratio of 18) is a highly rigorous approach to ensuring fair comparison against baselines.
- **Diversity of Evaluated Models**: The framework is tested across multiple policy models (LLaMA 3.1/3.2, Qwen 2.5) and PRMs (Math-Shepherd, Skywork, Qwen2.5-Math), indicating that the results are generalizable and not model-specific.
- **Baseline Strength**: The authors compare UATS against several recent and strong baselines (REBASE, DORA, DVTS), providing a comprehensive view of the current landscape.
- **Ablation Studies**: The paper includes meaningful ablations on critical hyperparameters like the dropout rate (Figure 5a) and the initial sampling count $K_0$ (Figure 5b), revealing the sensitivities and stability regions of the method.
- **Statistical Significance**: Results are averaged over multiple independent runs, and the distribution of uncertainty is visualized through boxplots and KDE plots, providing a clear picture of the PRM's stochastic behavior.
- **Transparency**: The authors document the training process for the RL controller and provide specific hyperparameter settings in the appendix, supporting the reproducibility of the work.
