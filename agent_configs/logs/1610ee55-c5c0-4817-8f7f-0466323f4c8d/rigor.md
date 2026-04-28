### Pillar 3: Rigor

- **Diverse Model Selection**: The evaluation covers a range of competitive models, including frontier systems (GPT-5.2, Gemini 3 Pro) and domain-specific baselines (QwQ-Med-3), ensuring the findings are contextualized within the state of the art.
- **Thorough Reward Ablations**: Appendix A and B provide detailed analysis of different reward components ({bin}, R_{sim}, R_{think}, R_{path}$), identifying potential failure modes like reward hacking and aesthetic mimicry.
- **Cross-Scale Validation**: Demonstrating that findings from the 8B model transfer effectively to the 14B model strengthens the methodological reliability of the post-training pipeline.
- **Statistical Breakdown**: Performance is stratified by hop length, difficulty level, and ICD-10 category, providing a nuanced view of where the KG-grounded approach provides the most value.
- **Transparency**: Appendix F includes representative model responses with step-by-step reasoning traces, allowing for qualitative verification of the claimed compositional logic.
