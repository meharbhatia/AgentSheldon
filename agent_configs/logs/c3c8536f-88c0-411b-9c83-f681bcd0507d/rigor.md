# Pillar 3: Rigor

The paper exhibits a high level of experimental and theoretical rigor, though some areas for clarification remain.

## Baselines
The paper compares against appropriate and strong baselines:
- **MFVI (Mean-Field Variational Inference)**: A standard baseline for VI.
- **GC-VI (Gaussian Copula VI)**: Represents prior work using copulas for VI.
- **MAF (Masked Auto-regressive Flows)**: A more complex, non-linear variational family.
- **NUTS (No-U-Turn Sampler)**: Used as ground truth for posterior contours.

The comparison is fair, as the authors mention adjusting GC-VI parameters to make the comparison practical (lines 1787-1788).

## Compute Fairness
The authors acknowledge the high sampling cost of simultaneous vine parameter estimation (lines 093-095) and position their stepwise approach as a more efficient alternative. They provide a reduction in MC samples (from 1024 to 10) for baseline GC-VI to enable its evaluation, which is a pragmatic if potentially slightly biased choice (favoring their own method if 10 samples are insufficient for simultaneous estimation).

## Ablations and Simulation Study
The intensive simulation study in Appendix H is a highlight of rigor. Analyzing the effect of alpha across 3 different setups and 10 examples per setup provides meaningful evidence for the choice of alpha=0.1. The use of relative KL divergence (Eq 29) to handle different example scales is statistically sound.

## Dataset Selection
The paper uses both toy examples (Independence, Needle) to demonstrate fundamental properties and a real-world benchmark (`pumadyn32nm` for SGPR). The choice of `pumadyn32nm` follows established setups (Lázaro-Gredilla & Figueiras-Vidal, 2009).

## Reproducibility
The authors provide:
- Clear algorithmic description (Algorithm 1).
- Specification of hyperparameters (alpha=0.1, R-hat threshold, Kendall's tau threshold).
- Detailed description of competitor models and their settings (Section I).
- Promise of code release upon acceptance.

One minor rigor concern: The SGPR experiments (Fig 3 & 4) show that the global stopping criterion did not trigger until t=46, suggesting that for high-dimensional inducing point spaces, the "parsimony" claim might be weaker than in low-dimensional settings, or that the greedy tree structure is indeed sub-optimal as suspected.
