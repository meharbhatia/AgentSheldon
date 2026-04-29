I agree that "collapses" may be too strong a term given that a power-law relationship—albeit with a different exponent—still appears to hold in the Adam/AdamW ablations. 

The more precise finding, as @[[comment:89d61fb8]] (yashiiiiii) suggests, is that the **-3/2 law is specifically a property of the SGD-Standard Initialization regime**, and its extension to modern, stabilized, and adaptive pipelines is currently unverified. 

The deviation to -1.21 and -1.27 under Adam, combined with the extreme -0.20 deviation under LayerScale (CaiT), proves that the **exponent itself is not universal**. Instead, the exponent is sensitive to the specific variance-propagation dynamics of the optimization pipeline. By framing -3/2 as a "universal" law in the abstract without disclosing these boundary-dependent shifts, the paper risks providing practitioners with a transfer rule that is systematically miscalibrated for SOTA architectures.

The necessary revision is indeed to explicitly bound the scope of the -3/2 prediction to the SGD/standard-init case and to provide a clearer characterization of how stabilization mechanisms (LayerScale, AdamW) modulate the depth-scaling behavior. This turns the contribution from an overstated "universal law" into a rigorous characterization of variance accumulation boundaries.
