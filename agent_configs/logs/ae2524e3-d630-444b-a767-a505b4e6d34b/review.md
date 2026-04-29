# Review: Bird-SR: Bidirectional Reward-Guided Diffusion for Real-World Image Super-Resolution

Bird-SR introduces a principled bidirectional reward-guided diffusion framework designed to address the distribution shift between synthetic training data and real-world low-resolution images. By jointly optimizing forward synthetic processes with relative rewards and reverse real-world trajectories with semantic-aligned feedback, the method achieves significant perceptual improvements without compromising structural fidelity.

## Strengths

- **Principled Bidirectional Framework:** The core idea of coordinating forward (synthetic) and reverse (real-world) optimization is a conceptually elegant solution to the domain gap in Real-ISR.
- **Robustness to Reward Hacking:** The integration of **relative reward** anchoring to ground truth and **semantic alignment** via DINO features effectively mitigates the risk of hallucinating unrealistic textures—a common failure mode in perceptual optimization.
- **Strong Empirical Performance:** Bird-SR consistently outperforms state-of-the-art diffusion baselines (SeeSR, SUPIR, DreamClear) across four diverse real-world benchmarks in non-reference perceptual metrics.
- **Excellent Qualitative Evidence:** The manuscript provides high-quality visualizations and qualitative comparisons that clearly demonstrate superior fine-texture recovery and structural consistency.
- **Actionable Dynamic Weighting:** The trajectory-aware distortion-perception weighting strategy ($\lambda(t)$) provides a practical mechanism for balancing fidelity and realism across diffusion timesteps.

## Weaknesses

- **Absence of Statistical Rigor:** The primary results (Tables 1, 3, 4, 7, 8) lack standard deviations, variance reporting, or statistical significance tests. Given the stochasticity of RL-based fine-tuning and diffusion sampling, the reliability of the reported margins is difficult to assess.
- **Metric Reporting Inconsistency:** Table 1 employs a non-standard reporting format, mixing absolute scores for most baselines with relative deltas ($\uparrow \Delta$) for others. This complicates direct comparisons and potentially overstates relative gains.
- **Small-Scale Perception Validation:** While the user study is welcome, it only evaluates 40 images—less than 10% of the total benchmark set. A more comprehensive subjective evaluation would strengthen the claims of perceptual superiority.
- **Heuristic Timestep Restriction:** The decision to focus reward supervision strictly on the final timestep ($t=0$) for real-world data (Section 4.2) is motivated by Figure 2 but lacks an ablation showing why mid-trajectory rewards are less effective or potentially harmful.

## Questions

1. Can the authors provide standard deviations or confidence intervals for the main results in Table 1 across multiple training seeds?
2. Why was the decision made to report only relative deltas for the ResShift baseline in Table 1, and can the absolute scores be provided for transparency?
3. Did the authors investigate the impact of applying the semantic alignment constraint ($\mathcal{L}_{sem-align}$) at intermediate timesteps rather than only at the final step?
4. How sensitive is the framework to the choice of the spatial semantic feature extractor (e.g., using CLIP instead of DINOv2)?

## Recommendation

Bird-SR is a high-quality, technically solid contribution that successfully applies trajectory-level preference optimization to the challenging domain of real-world super-resolution. The bidirectional framework and the semantic alignment mechanism provide a robust and principled path toward more realistic image restoration. While the empirical reporting would benefit from more rigorous statistical treatment and consistent formatting, the overall conceptual value and qualitative success justify a recommendation for acceptance.

**Recommendation: 5 — Accept**
Technically solid; provides a principled solution to a high-impact problem in Real-ISR with strong empirical and qualitative support.
