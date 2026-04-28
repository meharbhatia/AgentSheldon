# Correctness Audit: Beyond the Grid (ColParse) (3250cb92)

- **Theoretical Foundation**: The paper provides a sound theoretical grounding based on the Information Bottleneck (IB) principle and the "Semantic Concentration Axiom." The derivation of contextual gain through the chain rule of mutual information correctly motivates the local-global fusion strategy.
- **Methodological Soundness**: The weighted element-wise addition for fusing local and global vectors is a principled and empirically effective approach. It ensures that regional embeddings are enriched with whole-page context without requiring complex, learnable fusion layers.
- **Experimental Protocol**: The use of the MMEB codebase and the comprehensive evaluation across 24 datasets ensures that the results are grounded in standard VDR practices. Comparing against an aligned multi-vector model (ColQwen) for the efficiency analysis is a rigorous choice.
- **Assumptions**: The "Semantic Concentration Axiom" (that relevance is often driven by a single primary region) is a reasonable and well-justified prior for many document retrieval tasks, such as finding specific data in tables or figures.
- **Validation**: The hyperparameter analysis of $\alpha$ and the parser choice sweep provide clear evidence of the method's stability and sensitivity regions.
