**Strengths**

- **Theoretically Elegant Bridge:** The formal proof (Theorems 3.1 and 3.2) linking deterministic optimal control to randomized Gaussian policies in continuous-time RL is a significant and well-executed mathematical contribution.
- **Strong Empirical Performance:** ART-RL consistently outperforms the standard EDM and Uniform schedules across multiple datasets (CIFAR-10, ImageNet, etc.), particularly in the low-NFE regime (NFE < 10), addressing a critical practical bottleneck.
- **Demonstrated Transferability:** The ability to apply a schedule learned on one dataset zero-shot to others of different resolutions is a practically valuable finding that increases the utility of the approach.
- **High Mathematical Clarity:** The manuscript is exceptionally well-written, with a clear and logical transition from standard diffusion mechanics to the proposed optimal control relaxation.

**Weaknesses**

- **Methodological Redundancy:** A critical inspection of the system dynamics reveals that the geometric state trajectory is invariant to the control variable $\theta(t)$. Consequently, the motivated optimal control problem reduces to a 1D integral that possesses a known **closed-form analytical solution** ($\theta^* \propto |Q|^{-1/2}$). Applying complex, exploratory continuous-time RL to a problem with an exact analytic solution represents a significant case of methodological over-engineering.
- **Omission of Critical Baselines:** The paper fails to cite or compare against state-of-the-art principled scheduling methods such as **Watson et al. (ICLR 2022)** and **Sabour et al. (ICML 2024, "Align Your Steps")**, which also target the minimization of discretization error. Furthermore, comparisons against textbook **adaptive step-size ODE solvers** (e.g., dopri5) are missing.
- **High Training Overhead:** The reliance on Jacobian-vector products (JVP) of the score network for the reward signal introduces substantial computational costs during the RL training phase. The manuscript lacks a transparent analysis of this overhead compared to training-free or direct analytical scheduling.
- **Solver-Objective Mismatch:** The objective is derived from first-order Euler truncation error, yet it is evaluated using the higher-order Heun solver in the EDM pipeline. The optimality of an Euler-optimized grid for higher-order schemes is not rigorously established or ablated.

**Questions**

1. How do the authors justify the use of complex actor-critic RL when the motivated control problem possesses a closed-form analytical solution ($\theta^* \propto |Q|^{-1/2}$)?
2. Can the authors provide a direct empirical comparison between the learned ART-RL schedule and the analytical schedule derived from the same $|Q|$ proxy?
3. What is the total wall-clock training time for the ART-RL policy compared to the time saved during the inference phase?

**Recommendation: 3 — Weak Reject**

While the framework is mathematically elegant and empirically effective, its scientific necessity is undermined by the existence of a closed-form analytical solution to the motivated control problem and the omission of key recent baselines that address the same objective.
