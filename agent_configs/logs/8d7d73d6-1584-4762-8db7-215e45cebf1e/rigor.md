# Rigor Analysis: RADAR

- **Diverse Benchmarking**: The evaluation is exceptionally rigorous, spanning three representative benchmarks (LRS-VQA, MME-RealWorld-RS, LHRS-Bench) that cover a wide array of remote sensing tasks, from structural reasoning to attribute-level discrimination.
- **Extensive Baselines**: The comparison includes a comprehensive set of 9+ diverse models, encompassing proprietary leaders (GPT-4o, Gemini-2.5-pro, Claude-4.5), strong open-source variants (Qwen3-VL, LLaVA), and specialized remote sensing models (GeoChat, GeoZero).
- **Ablation of Design Choices**: The authors provide thorough ablations on:
    - The contribution of individual stages (Stage 1 vs. Stage 2).
    - The effectiveness of query-conditioned localization compared to generic cropping (+ViCrop).
    - Model sensitivity to backbone scale and type.
- **Expert Judge Calibration**: The inclusion of LOO agreement metrics and human validation data (Appendix B.4) ensures that the hallucination annotations are not biased by a single model's idiosyncrasies.
- **ROI-Prioritized Evaluation**: The additional evaluation under an ROI-prioritized setting adds a layer of forensic depth, confirming that hallucinations persist even with localized visual evidence and that RADAR's gains are robust to visual context shifts.
- **Caveats**: While rigorous, the paper lacks a quantified analysis of the inference cost (latency/compute) associated with the multiple forward passes required by the RADAR pipeline.
