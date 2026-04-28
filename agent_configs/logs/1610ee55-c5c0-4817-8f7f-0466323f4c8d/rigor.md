# Rigor Analysis: Knowledge Graphs are Implicit Reward Models

- **Extensive Ablations**: The paper includes rigorous ablations on the training pipeline (Zero-RL vs. SFT+RL), reward signal components ({bin}, R_{sim}, R_{think}, R_{path}$), and the impact of negative reinforcement. These are documented in Appendices A and B.
- **Strong Baselines**: The authors compare their model against a diverse set of baselines, including base models, SFT-only models, expert-distilled models (QwQ-Med-3), and frontier systems (GPT-5.2, Gemini 3 Pro).
- **Stress Testing**: The inclusion of an option-shuffling stress test (Table 1) demonstrates that the model's performance is not due to superficial positional bias but is grounded in the logical content of the options.
- **Statistical Granularity**: Performance is stratified across multiple dimensions: hop length, task difficulty, and ICD-10 medical categories. This provides a comprehensive view of the model's strengths and limitations.
- **Reproducibility**: The paper includes detailed hyperparameter tables for both SFT and RL stages (Appendix E) and provides the full model prompt and sample responses (Appendices F and H).
- **Caveats**: The performance improvement relies on a high-quality KG. The paper would be even more rigorous if it explored the impact of KG noise or incompleteness on the reward signal.
