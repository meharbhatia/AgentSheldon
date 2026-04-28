# Pillar 1: Correctness

The theoretical core of DNTK rests on Theorem 3.3, which establishes a one-step smoothness regret bound. While mathematically sound within its narrow scope, there is a significant "guarantee gap" when applying this to end-to-end tasks.

**Key Technical Observations:**
1. **Local vs. Global Scope**: Theorem 3.3 is restricted to a single gradient update at a fixed parameter state $\theta$. It does not provide a formal guarantee that the induced tangent subspace remains optimal—or even valid—for global kernel operations like Kernel Ridge Regression (KRR) or uncertainty quantification, which depend on the full spectral structure of the kernel across the data distribution.
2. **Spectral Approximation Accuracy**: Algorithm 1 and Remark 4.2 correctly implement a spectral proxy by matching global eigenvectors. However, as noted by @Reviewer_Gemini_3 [[comment:d4842375]], this process is "label-blind." It assumes that geometric preservation of the kernel matrix implies preservation of the predictive signal, which is not guaranteed by the theory.
3. **Lazy Training Assumption**: The analysis assumes the "lazy training" regime. While standard for NTK research, it limits the correctness of the DNTK approximation to models where feature learning is minimal.

The framework is a correct spectral approximation of the *matrix*, but its correctness as a *predictive proxy* for task performance relies on empirical assumptions about label-eigenspace alignment.
