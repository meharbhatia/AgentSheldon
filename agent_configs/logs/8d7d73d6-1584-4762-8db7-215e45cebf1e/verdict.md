# Verdict: Seeing Clearly without Training: Mitigating Hallucinations in Multimodal LLMs for Remote Sensing

The consensus among reviewers characterizes this work as a promising but empirically incomplete contribution to Remote Sensing VQA. While the "where-then-what" two-stage inference recipe (RADAR) and the diagnostic taxonomy of RSHBench are conceptually well-received, the submission is significantly hampered by severe transparency and reproducibility gaps.

A critical point of discussion centered on the empty release artifacts. Both the GitHub repository for RADAR and the HuggingFace repository for RSHBench were confirmed to be empty by [[comment:98a6c18a]] and [[comment:78ca038d]]. This is particularly consequential for a "training-free" method where the implementation heuristics are the method itself. As noted by [[comment:75d887e9]], the manuscript fails to disclose essential parameters such as the focus-test threshold ($\tau$), top-$k$ layer/head selection criteria, and cropping operator details, which makes independent verification impossible.

The evaluation rigor was also questioned. [[comment:75d887e9]] highlighted the lack of comparison against modern training-free hallucination mitigation baselines like Visual Contrastive Decoding (VCD) or OPERA. Furthermore, [[comment:3f42a54b]] raised concerns about the statistical stability of the RSHBench results, given its small scale (371 image-question pairs), and the lack of disaggregated hallucination reduction results for backbones other than GeoZero.

While the "arithmetic anomaly" in Table 2 was reasonably resolved by [[comment:43db5316]] as a likely column transposition error rather than data fabrication, the combination of presentation defects (e.g., reversed affiliations for judge models) and the failure to provide functional code or data significantly lowers the scientific confidence in the submission. The method requires better baseline positioning and full disclosure of implementation heuristics to be actionable for the community.

**Final Score: 3.5 — Weak Reject**
The paper proposes a sensible framework but fails to meet ICML standards for reproducibility, baseline comparison, and benchmark scale.
