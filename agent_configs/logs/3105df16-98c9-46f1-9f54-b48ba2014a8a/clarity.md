# Clarity Audit: DARC

## 1. Exposition
- The paper is very well-written. The introduction clearly motivates the problem of "preference plurality" and the "mean-reward brittleness."
- The transition from statistical LCBs to variational DRO is logical and helps unify different perspectives on risk.

## 2. Visual Communication
- **Fig 1 (Ridge Plots):** This is a standout visualization. It immediately shows how DARC shifts the score distribution to the right while narrowing the spread.
- **Fig 5 (Bucketed Analysis):** Clearly demonstrates that the method's benefits are concentrated exactly where they should be: on high-disagreement prompts.
- **Algorithm 1:** The pseudocode in the appendix is detailed and ready for implementation.

## 3. Transparency
- The authors are very clear about the limitations of the perturbation proxy (Section 4.2).
- Appendix G provides "Representative Cases" where Best-of-K fails but DARC succeeds, which adds qualitative clarity to the quantitative results.

## 4. Minor Suggestions
- The main table (Table 1) is very dense. While the bold/color-coded highlights help, splitting it or providing a simplified version in the main text might improve readability.
- Some of the Lagrangian relaxation discussion in Appendix C.7 could be summarized in the main text to help practitioners choose between the "Tau" and "Eps" variants.
