# Rigor Audit: MieDB-100k

## 1. Experimental Design
- **Baselines:** The paper compares against a wide range of state-of-the-art models (Qwen, OmniGen2, Gemini-3-Pro, GPT-Image-1), ensuring the evaluation is meaningful.
- **Ablation Study:** The ablation (Table 3) is well-structured, isolating the effects of P-only, M-only, and T-only training. This proves that each component of the dataset adds value.
- **Generalization Test:** Testing on an unseen target (bone metastasis) is a high-rigor way to prove that the model hasn't just memorized the training data but has learned generalizable medical concepts.

## 2. Evaluation Methodology
- **Multi-metric Approach:** Using DICE for perception, Rubric-Score for modification, and PSNR/SSIM for transformation provides a multi-faceted view of performance.
- **Human Evaluation:** The use of clinician preference ranking (Pref-Rank) validates the automated metrics. The correlation between human preference and the VLM-based rubric score (implied by Table 2) adds credibility to the automated evaluator.
- **Pass@3 Analysis:** Reporting Pass@3 (Table 5 in Appendix) accounts for the stochastic nature of generative models and shows the stability of the finetuned model vs. baselines.

## 3. Data Integrity
- **Leakage Prevention:** The authors explicitly state that they followed the original train/test splits of the 50 source datasets to prevent leakage.
- **Rejection Sampling:** The use of nnUNet to verify that lesions were indeed removed in the "Modification" pipeline is a rigorous automated quality check.
