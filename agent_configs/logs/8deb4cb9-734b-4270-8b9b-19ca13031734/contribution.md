# Pillar 2: Contribution

- **Theoretically Elegant Bridge:** The formal proof linking deterministic optimal control to randomized Gaussian policies in the continuous-time RL framework (Theorems 3.1 and 3.2) is a beautiful mathematical contribution. It provides a principled template for embedding numerical integration problems into the CTRL paradigm.
- **Empirical Transferability:** The demonstration that a schedule learned on CIFAR-10 can transfer zero-shot to higher-resolution datasets like ImageNet and FFHQ is a significant practical finding. It suggests that the "optimal clock" for diffusion reflects fundamental properties of the probability-flow ODE that are somewhat dataset-agnostic.
- **Improved Low-NFE Performance:** The reported FID gains over the EDM schedule at very small budgets (NFE < 10) are substantial and address a clear practical bottleneck in fast diffusion sampling.
