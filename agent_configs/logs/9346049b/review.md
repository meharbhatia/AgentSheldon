# Review: From Unfamiliar to Familiar: Detecting Pre-training Data via Gradient Deviations in Large Language Models

This paper proposes GDS, a gradient-based framework for pre-training data detection using features extracted from LoRA matrices. While the empirical results show significant improvements over likelihood-based baselines, the methodology relies on a fundamentally flawed interpretation of neural network weight structures and lacks the necessary rigor to account for stochasticity.

## Strengths
- **Empirical Performance**: The reported AUROC and TPR@5%FPR scores are impressive and consistently outperform strong baselines like Min-k% and FSD across multiple datasets and models.
- **Efficiency**: Leveraging LoRA gradients for a single backpropagation pass is a computationally efficient way to probe internal model dynamics without requiring full parameter updates.
- **Artifact Check**: The modification experiment on WikiMIA (removing timestamps) demonstrates a proactive effort to ensure the method is not merely capturing obvious dataset-specific artifacts.

## Weaknesses
- **The Eccentricity Fallacy**: The "Row/Column Eccentricity" features (Eq. 11-12) assume that neuron indices $i$ and $j$ have spatial meaning relative to a "matrix center." This is mathematically incorrect for linear layers, which are permutation-invariant. Any signal captured by these features is likely a model-specific neuron bias rather than a generalizable "gradient deviation law."
- **Theoretical-Implementation Disconnect**: The paper motivates the framework using dynamic "evolutionary trends" over 8 epochs, but the proposed method is a static, single-pass measurement at $t=0$. The claim that $t=0$ gradients capture the transition from "unfamiliar to familiar" lacks a rigorous logical bridge.
- **Unaccounted Stochasticity**: LoRA gradients are functionally dependent on the random initialization of the **A** matrix. The paper does not report results across multiple random seeds or analyze the stability of the feature vectors, leaving the robustness of the method in question.
- **Biased Comparison**: The GDS method benefits from a supervised MLP classifier trained on 30% of the target data. Comparing this supervised approach to unsupervised or zero-shot baselines like Min-k% without a similarly supervised likelihood control overstates the contribution of the gradient features themselves.

## Questions for the Authors
1. How do you justify the use of row/column indices in the "Eccentricity" formula, given that neuron ordering in a linear layer is arbitrary?
2. Why is the motivation based on multi-epoch training dynamics (Section 3) when the actual detection method is a static, one-pass measurement at $t=0$ (Section 4)?
3. Have you evaluated the stability of the GDS features across different random seeds for the LoRA **A** matrix?
4. How would a supervised MLP classifier trained purely on token-level likelihoods or PPL distributions compare to your gradient-based approach?

## Recommendation
**Reject (Score: 2.5)**
Despite strong empirical numbers, the central methodology is built on a mathematical fallacy (spatial interpretation of latent indices) and a logical disconnect between theory and implementation. The lack of stochasticity analysis further undermines the reliability of the work.
