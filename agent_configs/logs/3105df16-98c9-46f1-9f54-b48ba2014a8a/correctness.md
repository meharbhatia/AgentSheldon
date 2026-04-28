# Correctness Audit: DARC

## 1. Theoretical Soundness
- **KL-DRO Equivalence:** The derivation of the entropic decoding objective from KL-based distributionally robust optimization (Theorem 3.4) is correct and follows established principles of risk-sensitive control (Donsker-Varadhan variational formula).
- **LCB Derivation:** Proposition 3.2 correctly applies the empirical Bernstein inequality to derive a uniform lower confidence bound. The $1/\sqrt{n}$ scaling with empirical standard deviation $\hat{\sigma}$ is the correct leading term for capturing variance-dependent uncertainty.
- **$\chi^2$-DRO Relation:** The connection between mean-dispersion (mean-variance) surrogates and $\chi^2$-DRO (Proposition 3.5) is mathematically sound, providing a clear variational interpretation for common heuristics.

## 2. Proxy Validity
- The core empirical claim for "Correctness" in a practical setting is the validity of the perturbation-sensitivity proxy ($\hat{\sigma}$) for human disagreement.
- The paper provides strong evidence in Fig 8 (Spearman $\rho = 0.65$) and through partial correlation analysis (controlling for length and mean reward). This level of correlation is sufficient to justify $\hat{\sigma}$ as a "screening signal," though not as a perfect estimator.

## 3. Potential Concerns
- **Independence Assumption:** The LCB derivation assumes i.i.d. satisfaction samples for each candidate. While human raters might be independent, proxy scorers based on ensembles or perturbations likely have correlated errors. The paper addresses this in Appendix C.5 by showing the guarantee holds with an additive slack term under uniform proxy error, which is a reasonable technical compromise.
- **Non-negativity in DRO:** The $\chi^2$-DRO closed form (Eq 12) requires a non-negativity condition on the extremal density. The paper correctly notes this (Prop 3.5) and explains that the mean-dispersion form remains a valid (pessimistic) lower bound even when the condition fails.
