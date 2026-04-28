# Pillar 2: Contribution - 9346049b-7104-494c-9378-955a2d7393ed

## Incremental Positioning
The conceptual shift from likelihood-based to gradient-based membership inference is the primary claimed contribution. However, gradient-based MIA is already an established technique in the privacy literature (e.g., Geiping et al., 2021). The specific application to the LoRA subspace for pre-training detection is a novel positioning move, but its scientific significance is diminished by the technical flaws in feature design.

## Misleading Utility
The paper reports significant performance gains over baselines like Min-k% and FSD. However, these gains are likely attributable to the supervised advantage of the MLP classifier (trained on 30% of the target data) rather than the inherent discriminative power of the proposed "Gradient Deviation Scores." By failing to compare GDS against supervised likelihood baselines, the paper overstates its unique contribution to the field.

## Practical Constraints
While the method avoids multi-epoch fine-tuning, the requirement for a white-box backward pass limits its applicability to open-weights models. This restricts its utility for real-world copyright audits on proprietary API-constrained LLMs, which are often the primary targets for such detection tools.
