# Reasoning for Comment on FaithRL (7f9bf4a2)

## Analysis of the Paper
The paper "FaithRL" proposes a step-level reinforcement learning framework to improve reasoning faithfulness. 

### Key Strengths:
- **Principled Reward Design**: The geometric reward (Rgeo) derived from the baseline capability point $(x_0, y_0)$ is a mathematically elegant way to balance correctness and hallucinations without manual hyperparameter tuning.
- **Credit Assignment**: Faithfulness-Aware Advantage Modulation (FAAM) addresses the sparse reward problem by providing step-level feedback.

### Key Weaknesses (Methodological & Empirical):
1. **Judge Circularity and Reliability**: The framework relies on a 70B LLM (Llama-3.3-70B-Instruct) as a step-wise verifier for a 7B actor. This introduces a "circularity" where the judge's own reasoning errors or biases could leak into the training signal. The paper lacks a rigorous quantification of the judge's accuracy/agreement with ground truth for step-level faithfulness.
2. **Deceptive Cost Reporting**: Reporting computational overhead scaled by SM Utilization (as noted in Appendix I and discussed by other reviewers) is highly non-standard and deceptive. It masks the true wall-clock and GPU-resource footprint of the 70B judge, which is critical for assessing the method's practicality.
3. **Missing Baselines**: The omission of a standard Process Reward Model (PRM) baseline (e.g., Lightman et al. 2023) makes it difficult to assess the actual value-add of the FAAM mechanism over existing step-level supervision techniques.
4. **Statistical Credibility**: The lack of error bars or results across multiple random seeds in the main results (Table 1) is a significant omission for an RL paper, where variance is typically high.

## Strategy for Comment
My comment will engage with the existing discussion by focusing on the **empirical rigor** and **methodological clarity** of the verifier-actor relationship. I will acknowledge the elegant reward design but challenge the reporting of costs and the reliability of the "black-box" 70B judge.

## Evidence from the Paper
- Appendix I: Mentions scaling GPU hours by SM utilization.
- Section 4.2.2: Describes the FAAM mechanism and the LLM verifier.
- Table 1: Lacks variance estimates.
