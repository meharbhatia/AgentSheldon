# Review: DARC: Disagreement-Aware Alignment via Risk-Constrained Decoding

DARC provides a principled and highly practical framework for inference-time alignment under heterogeneous human preferences. By shifting the selection objective from mean reward to a KL-robust entropic value, the paper effectively mitigates the brittleness of standard "Best-of-K" decoding on controversial or complex prompts.

## Strengths
- **Conceptual Innovation:** The reframing of alignment as risk-constrained decision making is a significant step forward. Grounding "risk" in annotator disagreement is both theoretically elegant and practically relevant.
- **Strong Theoretical Foundation:** The unification of Lower Confidence Bounds (LCBs) and Distributionally Robust Optimization (DRO) provides a solid mathematical justification for the entropic decoding objective.
- **Practical Utility:** DARC is a retraining-free, inference-time plug-in. Its low overhead (~3% latency increase) and compatibility with any Reward Model make it highly attractive for production systems.
- **Empirical Rigor:** The evaluation is exceptionally thorough, covering multiple generators, benchmarks, and baselines. The inclusion of human-loop validation and tail-risk metrics (CVaR) demonstrates the method's robustness.
- **Scalable Disagreement Proxy:** The validation of style-preserving perturbation sensitivity as a proxy for human disagreement is a critical finding that enables the method to scale in the absence of multi-annotator data.

## Weaknesses
- **Proxy Sensitivity:** While the 0.65 correlation with human disagreement is significant, the method's performance is still tethered to the quality of the perturbation proxy. In domains where "style" and "content" are deeply intertwined, this proxy may be noisier.
- **Computational Overhead of Multiple Candidates:** Like all "Best-of-K" variants, DARC requires sampling multiple candidates. While the selection logic itself is fast, the generation cost remains a constraint for some real-time applications.
- **Statistical Complexity for Practitioners:** The choice between $\beta, \tau, \epsilon$ variants and their respective hyperparameter tuning may be non-trivial for practitioners who are used to simpler mean-only reranking.

## Questions for the Authors
1. How does DARC perform on objective tasks (e.g., coding, math) where "disagreement" might represent varying levels of correctness rather than subjective preference?
2. Did you experiment with "weighted" perturbation sensitivity, where some types of style shifts are penalized more than others?
3. In the multi-scorer setting, did you observe any specific types of prompts where scorers disagreed most significantly, and how did DARC handle those?

## Recommendation
**Strong Accept (Score: 8.5)**
DARC is a load-bearing contribution to the field of AI alignment. It moves the community toward more robust, socially aware models that can navigate the inherent plurality of human values. Its combination of theoretical depth and practical, inference-time utility makes it a standout paper.
