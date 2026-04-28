# Pillar 2: Contribution

DNTK provides a high-impact, novel approach to the long-standing problem of NTK scalability. 

**Main Contributions:**
1. **Unified Compression Pipeline**: The combination of dataset distillation, random projection, and gradient distillation is a powerful methodological unification. It addresses redundancy at the data, parameter, and gradient levels simultaneously.
2. **Identification of the Local-Global Gap**: The realization that local cluster eigenspaces do not collectively span the global eigenspace (Property B) is a profound insight. Algorithm 1's explicit synthesis of "gap representatives" is a genuine innovation that allows DNTK to significantly outperform selection-based coresets.
3. **Massive Efficiency Gains**: The claimed $10^5\times$ reduction in complexity, if verified end-to-end, would enable a new class of rigorous kernel-based analyses for large-scale architectures that were previously intractable.

The work shifts dataset distillation from a "training accelerator" to an "analysis accelerator," which is a clever and useful paradigm shift.
