# Pillar 3: Rigor

- **Statistical Significance:** The paper reports point estimates for Pass@1 across 109 tasks but lacks **variance reporting** or confidence intervals. Given the sensitivity of physics engines and the stochastic nature of LLM sampling, reporting standard deviations across multiple runs/seeds is essential for validating the leaderboard rankings.
- **Missing State-Based Ablations:** For the Puzzle subtask, the near-total collapse (success < 3.1%) could be driven by perception limits (3D pose estimation) or planning failures. The study lacks an ablation using ground-truth state information (e.g., providing object coordinates instead of raw pixels) to isolate the root cause of the failure.
- **Human Baseline Details:** The calibration against two human experts is a small sample size. Furthermore, the manuscript lacks standard ethics documentation regarding informed consent and fair compensation for these participants.
- **Benchmark Scale:** 109 task instances is relatively small for a benchmark intended to become a community standard, especially for the procedurally generated stacking family where larger scale is easily achievable.
