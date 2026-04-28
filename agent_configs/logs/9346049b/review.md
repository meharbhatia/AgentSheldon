# Review: From Unfamiliar to Familiar: Detecting Pre-training Data via Gradient Deviations in Large Language Models

This paper proposes GDS, a framework for pre-training data detection that leverages gradient features extracted from a zero-initialized LoRA subspace. While the conceptual shift toward optimization-based signals is interesting, the manuscript suffers from fundamental mathematical fallacies and a structurally unfair experimental setup that significantly undermines its claims.

## Pillar 1: Correctness
The most critical technical flaw is the **Latent Space Eccentricity Fallacy** (Eqs. 11 & 12). The authors treat linear weight indices as spatial coordinates to measure "eccentricity," ignoring the fact that hidden dimensions in Transformers are permutation-invariant. Indices carry no topological information, making these spatial metrics mathematically meaningless. Furthermore, there is a stark **theoretical-implementation disconnect**: the framework is motivated by dynamic optimization laws but implemented as a static snapshot at $t=0$, failing to capture the described "evolutionary" behavior.

## Pillar 2: Contribution
The shift to gradient-based detection is a novel positioning move for pre-training MIA, but its significance is diminished by the reliance on flawed features. The reported gains appear to be a product of **supervised learning on labels** rather than the inherent discriminative power of the "Gradient Deviation Scores," as the method is not compared against baseline methods granted equivalent access to calibration data.

## Pillar 3: Rigor
The evaluation is characterized by **structural unfairness**: a supervised MLP classifier (GDS) is compared directly against zero-shot heuristics (Min-k%, PPL). Without baseline stratification, the algorithmic advantage of GDS is unproven. Additionally, the lack of variance reporting across multiple LoRA A random seeds and the **violation of double-blind policies** (direct GitHub link in Footnote 1) are significant rigor failures.

## Pillar 4: Clarity
The manuscript's narrative is potentially misleading, framing static measurements as "dynamic" and poor transfer performance (~0.66 AUC) as "significantly improved transferability." Notation overloading and splitting of equations further hinder clarity.

## Recommendation: Reject (Score: 3.0)
The paper rests on a mathematically unsound foundation regarding its "position" features and employs an unfair evaluation framework. Given these fundamental issues and the anonymity violation, the work is not yet suitable for publication at ICML.
