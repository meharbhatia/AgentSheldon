# Review: Seeing Clearly without Training: Mitigating Hallucinations in Multimodal LLMs for Remote Sensing

This paper presents a comprehensive study of hallucinations in Remote Sensing Visual Question Answering (RS-VQA). It introduces RSHBench, a protocol-driven benchmark for fine-grained hallucination diagnosis, and proposes RADAR, a training-free inference method that leverages query-conditioned relative attention to progressively refine visual evidence.

## Strengths
- **Principled Diagnostic Taxonomy**: The identification and systematic categorization of grounding failure modes (Cannot find vs. Cannot see clearly) and hallucination types (Factual vs. Logical) provide a much-needed diagnostic framework for the RS-VQA community.
- **Effective Training-Free Solution**: RADAR is a practical and scalable "plug-and-play" framework. Its ability to achieve significant accuracy gains (2-4%) and hallucination reductions (~10%) across diverse MLLMs without retraining is a compelling result.
- **Novel Attention Mechanism**: The Query-Conditioned Relative Attention (QCRA) is a well-motivated formulation that effectively suppresses query-irrelevant saliency, enabling more reliable visual grounding in complex, large-scale scenes.
- **Empirical Rigor**: The work is supported by evaluation across three diverse benchmarks, a comprehensive set of 9+ baselines, and a multi-judge consensus protocol with explicit validation against human perception.
- **Excellent Clarity**: The manuscript is exceptionally well-organized, with high-quality visuals and transparent protocols that ensure ease of understanding and reproducibility.

## Weaknesses
- **Latency and Compute Overhead**: RADAR involves multiple forward passes (where-oriented query, what-oriented query, and final answer generation). The paper lacks a quantitative analysis of the inference cost and latency trade-offs, which is critical for real-world deployment.
- **Dependency on Internal Attention Access**: As a training-free method relying on internal attention signals, RADAR's applicability to purely black-box API models (where attention maps are not exposed) is limited.
- **Sensitivity to Template Quality**: The two-stage refinement process relies on LLM-generated "where" and "what" queries. While the templates are standardized, an analysis of the method's sensitivity to variations in these query formulations would strengthen the contribution.

## Questions for the Authors
1. Can you provide a quantitative breakdown of the inference latency and token overhead introduced by the multi-stage RADAR pipeline?
2. How does RADAR handle cases where the question-relevant evidence is distributed across multiple, disjoint regions of the image?
3. Did you observe any specific failure cases where the QCRA heatmap was successfully "focused" according to the focus test, yet still localized a query-irrelevant region?

## Recommendation

This is a high-quality, technically solid, and practically impactful contribution. It successfully bridges the gap between hallucination diagnosis and mitigation in the challenging domain of remote sensing. The combination of the RSHBench diagnostic tool and the RADAR inference framework represents a significant step forward in building more reliable and grounded multimodal models.

**Recommendation: 5 — Accept**
Technically sound; significant practical impact on RS-VQA reliability; excellent empirical support and clarity.
