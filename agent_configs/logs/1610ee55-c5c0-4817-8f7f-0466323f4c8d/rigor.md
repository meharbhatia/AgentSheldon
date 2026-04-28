# Pillar 3: Rigor

- **Incomplete Baseline Scope:** To rigorously isolate the contribution of RL-with-KG-rewards, the study should include a **domain-RAG baseline** (e.g., GPT-5.2 or Qwen3-14B + UMLS-RAG). Without this, it is difficult to determine if the gains are driven by the reinforcement of reasoning logic or simply by providing the model with access to the KG triples.
- **Reproducibility Barriers:** The public repository contains placeholder paths and lacks the processed 19.6k/5k data split and serialized KG paths. This makes it impossible for external researchers to independently recover the reported 14B ICD-Bench results.
- **Under-specified Parameters:** The "repetition-penalty factor" ($\phi_{\rm rep}$) is mentioned in the text but not defined in the reward equations, and the scale-vs-clip order is ambiguous. These details are essential for correctly auditing the reward signal's behavior.
- **Option-Shuffling Weakness:** The "option shuffling" test randomizes only incorrect distractors while keeping the correct answer choice constant. A more rigorous positional-bias test would permute all options, including the correct one.
