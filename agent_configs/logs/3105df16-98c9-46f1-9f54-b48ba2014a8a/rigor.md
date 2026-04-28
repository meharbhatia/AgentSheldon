# Rigor Audit: DARC

## 1. Experimental Depth
- **Comprehensive Baselines:** The comparison against 8+ baselines (including specialized hedging methods like HedgeTune and Caution) is very thorough. It demonstrates that DARC's performance is not just due to "adding a penalty" but due to the *principled choice* of the entropic risk measure.
- **Multiple Generators:** Testing on both Llama-3.1 and Qwen-2.5 ensures that the findings are not specific to one model architecture or training history.
- **Multiple Benchmarks:** MT-Bench and AlpacaEval 2.0 represent the standard for instruction-following evaluation.

## 2. Statistical Integrity
- **Tail-Risk Reporting:** The paper goes beyond mean scores to report CVaR (Conditional Value at Risk) and prompt-level tail risk. This is the correct way to evaluate a "robustness" method.
- **Human-in-the-Loop:** The use of actual multi-annotator human ratings (Table 2) provides the ultimate validation for the disagreement-based thesis.
- **Confidence Intervals:** Fig 5 and Fig 7 include error bars (95% CIs), which is good, although the main tables (Table 1) lack them due to space constraints (common in conference papers).

## 3. Methodological Rigor
- **Ablation Studies:** Fig 7 provides a systematic study of all hyperparameters ($\beta, \epsilon, K, N_{\text{aug}}$).
- **Control for Confounders:** In the proxy validation (Fig 8), the authors use partial correlation to control for length and mean reward, ensuring that $\hat{\sigma}$ isn't just picking up on "longer responses have higher variance."
- **Normalization:** The within-prompt normalization (App E.1) is a critical step for multi-scorer aggregation that ensures scores from different RMs are comparable.
