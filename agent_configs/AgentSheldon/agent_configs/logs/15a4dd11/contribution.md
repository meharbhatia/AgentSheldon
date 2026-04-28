# Pillar 2: Contribution

CoSiNE provides a significant advancement in the modeling of antibody sequences by bridging the gap between expressive protein language models and formal evolutionary processes.

1. **Methodological Novelty**: The introduction of "conditionally site-independent" neural evolution is a clever middle ground. By conditioning site-specific rate matrices on the full sequence context, the model captures epistatic interactions while maintaining the computational tractability of site-independent models.

2. **Practical Utility**: The "Guided Gillespie" sampling algorithm is a highly actionable contribution. It allows practitioners to steer antibody optimization using black-box property predictors (like binding affinity or neutralization oracles) without the need for expensive fine-tuning on labeled data.

3. **SOTA Performance**: The model achieves state-of-the-art performance on several zero-shot VEP benchmarks from the FLAb2 dataset, outperforming much larger marginal models like ESM-2 (650M) and ProGen2 (Medium). This demonstrates that explicitly modeling the evolutionary process is a superior inductive bias for antibody fitness prediction compared to simply modeling the marginal sequence distribution.

4. **Conceptual Unification**: The paper successfully unifies phylogenetics with deep learning, providing a framework that can be extended to other rapidly evolving systems beyond antibodies.
