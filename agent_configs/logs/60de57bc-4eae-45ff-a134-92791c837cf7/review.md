**Strengths**

- **Principled Conceptual Taxonomy:** The division of DP synthesis into Causal, Graphical, and Predictive regimes is a significant contribution that provides much-needed clarity on the assumptions required for different types of task-specific synthesis and robustness.
- **Strong Theoretical Foundation:** The use of TV-distance surrogates to bound downstream prediction risk and the derivation of a closed-form optimal budget allocation elevate the method beyond simple engineering heuristics.
- **Automated Workload Construction:** By deriving the measurement workload directly from the target variable $Y$, PRISM lowers the deployment barrier for workload-aware DP mechanisms in predictive modeling scenarios.
- **Robustness Under Shift:** The SCM spurious-shift benchmark provides a compelling empirical demonstration of the advantages of structure-aware targeting over purely statistical correlation-based approaches.

**Weaknesses**

- **Confounded Experimental Results:** The comparison against task-agnostic synthesizers (MST, PrivBayes) is misaligned because PRISM benefits from an integrated feature-selection step that the baselines are denied. A fairer comparison against "DP Selection + MST" is missing, leaving it unclear if the gains are driven by PRISM's allocation math or simple dimensionality reduction.
- **Omission of Closest Baselines:** While the paper correctly identifies AIM and RAP++ as the most relevant workload-aware competitors, it fails to include them in the experimental results. This is a significant gap given PRISM's positioning as an advancement in workload-driven synthesis.
- **Heuristic Budget Splitting:** The split between the feature selection budget ($\varepsilon_{\rm sel}$) and the synthesis budget is hard-coded as a default heuristic (e.g., 10/90), which contradicts the paper's emphasis on a fully principled, risk-motivated allocation framework.
- **Oracle Structural Assumptions:** The performance of the Causal and Graphical regimes relies on perfect structural knowledge. The paper would be strengthened by a sensitivity analysis showing how the method handles noisy or partially misspecified causal graphs.

**Questions**

1. Can the authors provide results comparing PRISM against a "Standard DP Selection + MST" baseline to isolate the marginal benefit of the closed-form budget allocation?
2. How does the performance of PRISM compare to AIM when AIM is provided with the same Y-conditional workload derived in Section 5.3?
3. Is it possible to derive the optimal split between the selection budget ($\varepsilon_{\rm sel}$) and measurement budget analytically within the current risk-bound framework?

**Recommendation: 4 — Weak Accept**

PRISM provides an excellent conceptual framework and taxonomy for task-specific DP synthesis, but its empirical superiority remains partially unverified due to baseline misalignment and the omission of key workload-aware competitors.
