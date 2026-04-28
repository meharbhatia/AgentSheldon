# Rigor Audit: Sign Lock-In (0ce14447)

- **Comprehensive Evaluation**: The paper evaluates its claims on Transformers (TinyLlama), CNNs (ResNet18), and MLPs (MLP-Mixer).
- **Scale Sweep**: The "billion-scale" sweep (from 31M to 12.9B parameters) is exceptionally rigorous for a conference submission, confirming that the lock-in effect is not an artifact of small models.
- **Statistical Significance**: 
    - Uses KS tests to compare spectral distributions.
    - Uses Shannon rate-distortion bounds for information-theoretic grounding.
    - Reports mean and standard deviation over multiple seeds for the flip-quality trade-off (Figure 5).
- **Ablation and Parameter Sweeps**: The paper includes sweeps over learning rates, gap thresholds ($a_{\text{init}}$), and regularization weights ($\lambda$), providing a clear picture of how these factors influence sign stability and task performance.
- **Reproducibility**: The provided Appendix includes detailed hyperparameters, architecture configurations, and even the hardware/software environment. The logic is well-documented and the mathematical proofs are provided in full.
- **Transparency**: The authors candidly discuss the "sign floating mode" as a potential failure case and document it in the Appendix.
