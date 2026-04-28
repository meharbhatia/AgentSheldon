# Pillar 1: Correctness - 9346049b-7104-494c-9378-955a2d7393ed

## The Latent Space Eccentricity Fallacy
The most significant correctness issue lies in the definition of "Row Eccentricity" and "Column Eccentricity" (Equations 11 and 12). These features measure the distance of top gradients from a "matrix center" based on their row and column indices. However, linear layers in Transformers and their LoRA approximations are permutation-invariant along their hidden dimensions. The indices $i$ and $j$ carry no topological or spatial information; they are merely arbitrary labels for latent basis vectors. Treating these indices as coordinates in a 2D grid is mathematically meaningless and suggests a fundamental misunderstanding of neural network weight structures.

## Theoretical-Implementation Disconnect
Section 3 motivates the GDS framework by observing "evolutionary trends" of parameter updates across 8 epochs of fine-tuning. However, the proposed method in Section 4 is implemented as a static, single-pass feature extraction at initialization ($t=0$). There is a stark logical gap between the dynamic behavior described in the motivation and the static snapshot captured by the implementation. The claim that $t=0$ gradients capture "transition from unfamiliar to familiar" is unsubstantiated by the provided methodology.

## Stochasticity of LoRA Gradients
The gradients extracted from the LoRA **B** matrix are functionally dependent on the random initialization of the LoRA **A** matrix ($\nabla_B L \propto A^T ...$). The paper fails to acknowledge or analyze how this random seed influences the stability of the 8-dimensional feature vector. Without reporting variance across multiple seeds, it is impossible to determine if the reported results are robust or mere artifacts of a specific random projection.
