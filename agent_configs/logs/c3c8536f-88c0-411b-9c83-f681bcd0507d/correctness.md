# Pillar 1: Correctness

The paper's central theoretical claim is that standard backward KL-divergence (ELBO) optimization fails to recover the correct parameters for vine copula variational families when performed in a stepwise manner, whereas Rényi alpha-divergence (with low alpha) succeeds.

## Theorem 3.2 (Backward KL Failure)
The paper argues that minimizing the backward KL in a stepwise manner results in incorrect standard deviations and correlation matrices (unless all correlations are zero). The proof (Appendix E.2) relies on the specific sequence of optimization where marginals are fixed first. This claim is critical because it justifies the shift to Rényi divergence. The mathematical derivation in Appendix E.2 (Eq 1440-1447) shows that the derivative of the backward KL w.r.t. the first tree parameters does not vanish at the true correlation values because of the remaining dependence terms. This appears mathematically sound given the stepwise constraint.

## Theorem 3.1 (Forward KL Success)
The paper proves that forward KL (approximated by Rényi divergence with low alpha) does recover the true parameters in a stepwise manner for Gaussian cases. The derivation in Appendix E.1 (Eq 1027-1035) supports this. The link between Rényi alpha-divergence and forward KL as alpha -> 0 is well-established in prior literature (Li & Turner, 2016).

## Theoretical-Implementation Alignment
The method implementation (Algorithm 1) strictly follows the stepwise logic justified by the theory. The use of split-R-hat (Gelman et al., 2013) as a local convergence criterion is a clever application of MCMC diagnostics to optimization trajectories, though its reliability in this specific context (non-stationary chain of gradient steps) might be sensitive to the learning rate.

## Internal Inconsistencies
I found no major internal inconsistencies. The simulation study in Appendix H confirms that alpha=0.1 is a robust choice across various settings, supporting the choice made in the main text.

## Limitations
The "greedy" nature of the tree structure selection (for SGPR, Section 4.3) is acknowledged as potentially sub-optimal (lines 423-424), which is an honest assessment of a potential correctness/optimality trade-off.
