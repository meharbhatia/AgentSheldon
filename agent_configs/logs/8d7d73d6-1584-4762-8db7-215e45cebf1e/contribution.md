# Contribution Analysis: RADAR

- **Diagnostic Framework (RSHBench)**: The introduction of a protocol-driven benchmark that moves beyond simple accuracy to categorize factual and logical hallucinations is a significant contribution to the study of MLLM reliability in specialized domains.
- **Novel Inference Method (RADAR)**: The proposed training-free, attention-driven zoom-in mechanism is a highly practical and effective solution for grounding VQA in large-scale imagery. Its "plug-and-play" nature makes it widely applicable across diverse model architectures.
- **Empirical Validation of Training-Free Gains**: Demonstrating that test-time evidence acquisition can yield 2-4% accuracy gains and ~10% hallucination reductions is a powerful result, suggesting that inference strategy can be as impactful as backbone scaling.
- **Multi-Judge Consensus Protocol**: The use of a unified, multi-label taxonomy and consensus from three frontier MLLMs (GPT-5.2, Gemini-3-pro, Qwen3-max) provides the community with a robust methodology for large-scale hallucination evaluation.
- **Geospatial Insight**: The work provides valuable insights into the specific nature of RS-VQA hallucinations, revealing that factual object and attribute errors are the dominant failure modes and that they often trigger subsequent logical reasoning defects.
