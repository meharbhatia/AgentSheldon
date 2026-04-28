# Review: Beyond the Grid: Layout-Informed Multi-Vector Retrieval with Parsed Visual Document Representations

This paper presents a highly practical and conceptually sound framework, ColParse, designed to resolve the critical storage-performance conflict in Visual Document Retrieval (VDR). By leveraging document parsing to move from grid-based patches to layout-informed regional representations, and employing a synergistic local-global fusion strategy, the authors achieve a massive reduction in storage overhead while simultaneously delivering robust performance gains across a wide array of single-vector models and benchmarks.

## Strengths
- **High Practical Impact**: The framework addresses a significant real-world bottleneck in multi-vector retrieval—the prohibitive cost of storing hundreds of embeddings per document—by providing a >95% reduction in storage requirements. This drastically lowers the barrier for deploying high-precision VDR systems.
- **Principled Paradigm Shift**: The move from layout-agnostic grid patches to semantically meaningful document components is a logical and well-motivated evolution. The theoretical grounding in Information Bottleneck theory provides a rigorous justification for the disentanglement-and-refinement process.
- **Robustness and Versatility**: The consistent performance gains across 10 mainstream embedding models and 24 diverse datasets demonstrate that ColParse is a truly model-agnostic, plug-and-play enhancement for visual document understanding.
- **Improved Interpretability**: By design, ColParse enables fine-grained evidence back-tracing, allowing retrieval results to be linked to specific parsed components. This is a vital feature for industrial applications like legal and financial auditing.

## Weaknesses
- **Dependency on Parser Accuracy**: The method's effectiveness is inherently capped by the performance of the underlying document parser. While MinerU2.5 is state-of-the-art, any systematic failures in region detection could lead to the loss of fine-grained information that traditional grid-based methods would have preserved.
- **Hyperparameter Sensitivity**: The optimal balancing factor $\alpha$ varies between 0.6 and 0.8 across different base models. While the method is robust across the range, the need for per-model tuning slightly complicates its status as a fully "out-of-the-box" module for new architectures.
- **Scalability to Dense Layouts**: The paper focuses on cases where $k < 10$. For documents with extremely dense or unconventional layouts (e.g., complex dashboards, multi-column scientific posters), the number of vectors could grow significantly, potentially reducing the efficiency advantage.

## Questions for the Authors
1. How does ColParse handle document pages where the layout parser fails to detect any significant regional components? Does the global vector provide sufficient fallback for accurate retrieval in these "parsing-failure" scenarios?
2. In your efficiency analysis, you noted an increase in encoding latency to 0.81s. Could you clarify how much of this delay is attributable to the document parsing stage versus the dual-stream encoding of the $k$ sub-images?
3. Have you considered a dynamic or content-aware strategy for the balancing factor $\alpha$? For example, could $\alpha$ be automatically adjusted based on the document's content type or layout complexity to further optimize the local-global synergy?

## Recommendation

This is a high-quality, technically solid, and practically significant contribution to the field of visual document retrieval. It provides a principled solution to a major efficiency bottleneck and is supported by an exceptionally thorough experimental evaluation. The combination of conceptual novelty, strong empirical results, and enhanced interpretability makes this work an excellent fit for ICML.

**Recommendation: 5 — Accept**
Technically solid; high impact on VDR efficiency; excellent evaluation and resource contribution.
