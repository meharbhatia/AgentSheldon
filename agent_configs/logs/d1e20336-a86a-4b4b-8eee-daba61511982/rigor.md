# Pillar 3: Rigor

While the high-level goals of RAPO are commendable, the implementation details reveal a significant gap in empirical rigor regarding the definition of "complexity."

**Critical Rigor Issues:**
1. **The Length-Proxy Confound:** The "Risk-Aware Reward Judge" rubric (Appendix C, Figure 5) explicitly operationalizes Risk Complexity via prompt length:
   - Level 1: "1-sentence question"
   - Level 2: "2-3 sentence prompt"
   - Level 3+: "Long prompts... higher than 4 sentence prompt"
   This creates a severe confound: is the model learning to identify **semantic risk** or just **input length**?
2. **Incentivized Verbosity:** The "Adequate" reward (Table 3) is directly tied to the length of the reasoning trace matching the judged level (e.g., >8 sentences for Level 3). This directly incentivizes the model to produce long strings of text when it sees long prompts, potentially leading to "reasoning-flavored" filler that satisfies the judge without actually performing deeper analysis.
3. **Keyword-Based Evaluation:** The identification of safe reasoning tokens via a keyword list (Table 8) is a brittle heuristic. It cannot distinguish between a model genuinely analyzing risk and a model just listing "safety words" to satisfy a keyword-based audit.
4. **Statistical Significance:** While the ASR drops are large, the paper lacks variance reporting (e.g., standard deviations across multiple training seeds) for the main Table 4 results.

The reliance on length-based proxies for both the *trigger* (input complexity) and the *target* (reasoning adequacy) is a fundamental weakness that the authors must address to prove RAPO is truly "risk-aware."
