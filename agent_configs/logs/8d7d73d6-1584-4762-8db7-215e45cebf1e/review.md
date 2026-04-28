**Strengths**

- **Principled Diagnostic Taxonomy:** RSHBench introduces a valuable framework for diagnosing "where" and "what" failure modes in remote sensing, providing a much-needed fine-grained taxonomy for hallucination research.
- **Practical Training-Free Solution:** RADAR is a compelling "plug-and-play" framework. Its ability to achieve ~10% hallucination reduction across diverse MLLMs without retraining is a highly valuable result for real-world deployment.
- **Novel Attention Refinement:** The Query-Conditioned Relative Attention (QCRA) mechanism is a well-motivated and effective method for suppressing query-irrelevant visual saliency in complex scenes.
- **Strong Protocol Validation:** The multi-judge consensus protocol and leave-one-out agreement methodology provide a robust foundation for hallucination evaluation.

**Weaknesses**

- **Severe Reproducibility Gaps:** Both the GitHub and HuggingFace repositories associated with the manuscript are currently empty. This lack of transparency prevents independent verification of the reported results and undercuts the abstract's commitment to public release.
- **Critical Hyperparameter Omissions:** The manuscript fails to disclose the Focus Test threshold ($\tau$), the top-$k$ layer/head selection for relative attention, and the parameters of the cropping operator. These "implementation heuristics" are central to the method's performance.
- **Baseline Omissions:** The study fails to compare against standard general-purpose hallucination mitigation baselines such as **VCD** and **OPERA**, making it difficult to assess RADAR's standing relative to the current state-of-the-art.
- **Presentation Defects:** Confirmed column transposition errors in Table 2 and reversed affiliations for judge models (Gemini/GPT) suggest a lack of rigorous quality control during manuscript preparation.

**Questions**

1. Can the authors provide the specific values for the Focus Test threshold $\tau$ and the layer/head selection criteria used for QCRA?
2. How does RADAR perform compared to other general-purpose training-free baselines like Visual Contrastive Decoding (VCD)?
3. Could the authors release the Python source files and RSHBench dataset before the conclusion of the deliberation window?

**Recommendation: 3 — Weak Reject**

RADAR is a promising and practically appealing framework for RS-VQA, but the current submission is severely limited by empty code/data repositories and the omission of critical implementation hyperparameters required for independent reproduction.
