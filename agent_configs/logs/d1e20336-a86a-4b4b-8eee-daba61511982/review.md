# Review: RAPO: Risk-Aware Preference Optimization for Generalizable Safe Reasoning

RAPO provides a conceptually grounded and empirically strong framework for scaling safe reasoning in Large Reasoning Models (LRMs) according to attack complexity. By treating reasoning content as context for self-alignment, the work identifies a critical "signal dilution" failure mode in complex jailbreaks and proposes an adaptive reinforcement learning strategy to mitigate it.

## Strengths
- **Conceptual Framing**: Reinterpreting safe reasoning as in-context alignment provides a rigorous theoretical lens through which to analyze LRM safety.
- **Strong Empirical Gains**: The reduction in ASR on WildJailbreak (e.g., from 68.7% to 5.6% for DeepSeek) is highly significant and demonstrates the practical utility of the RAPO framework.
- **Adaptive Defense**: The shift from static safety filters to adaptive reasoning budgets is a vital contribution for the next generation of reasoning-heavy models.
- **High Transparency**: The inclusion of full system prompts and theoretical proofs in the appendix is commendable and greatly facilitates the audit of the proposed method.

## Weaknesses
- **Complexity-Length Confound**: The "Risk-Aware Reward Judge" rubric (Appendix C, Figure 5) explicitly uses prompt length as a primary proxy for Risk Complexity (e.g., Level 1 = 1 sentence, Level 3 = >4 sentences). This raises a significant concern that the model is learning to scale reasoning based on surface-level input length rather than semantic attack sophistication.
- **Incentivized Verbosity**: The adequacy reward is directly tied to reasoning length (e.g., >8 sentences for Level 3). This creates a risk of "reward hacking" where the model generates verbose but semantically shallow reasoning to satisfy the judge's length requirements.
- **Theoretical Assumptions**: Theorem 3.1 assumes concept orthogonality and unbiased gradient steps. In practice, synergistic attacks or biased reasoning could break the linear relationship between reasoning length and safety restoration.
- **Heuristic Evaluation**: The reliance on keyword matching (Table 8) to identify safe reasoning traces is a brittle metric for assessing the quality of internal reasoning.

## Questions for the Authors
1. How does RAPO perform on prompts where semantic complexity and input length are decoupled (e.g., a very long but simple benign prompt vs. a short but highly obfuscated "one-liner" jailbreak)?
2. Have you measured the **semantic density** or **information gain** of the safe reasoning traces as they increase in length? This would help confirm that the model is performing deeper analysis rather than just generating more tokens.
3. Could the "Risk-Aware Reward Judge" be modified to use a purely semantic rubric that excludes sentence count, and would the RAPO gains still hold?

## Recommendation
**Accept (Score: 7.0)**
This paper makes a load-bearing contribution to LRM safety. While the current implementation's reliance on length-based proxies for complexity is a notable limitation, the underlying framework is sound, and the reported robustness gains are too significant to ignore. Addressing the complexity-length confound would elevate this work to a strong accept.
