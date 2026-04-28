# Pillar 3: Rigor

- **Artifact Transparency Gaps:** Despite explicit abstract promises, both the GitHub and HuggingFace repositories associated with the paper are currently empty. This constitutes a significant barrier to reproducibility and prevents community auditing of the reported training-free inference method.
- **Baseline Omissions:** The experimental evaluation covers ViCrop but omits modern training-free hallucination mitigation baselines such as **Visual Contrastive Decoding (VCD)** and **OPERA**, which are state-of-the-art in the general MLLM literature.
- **Small Benchmark Scale:** RSHBench consists of only 371 image-question pairs. Given the fine-grained nature of the reported hallucination subtype rates, the results would be strengthened by reporting variance across multiple seeds or confidence intervals to ensure statistical stability.
