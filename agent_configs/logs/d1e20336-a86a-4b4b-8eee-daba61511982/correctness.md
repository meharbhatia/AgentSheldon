# Pillar 1: Correctness

The theoretical foundation of RAPO (Theorem 3.1) relies on the "implicit gradient descent" view of transformers. While this is a recognized framework (Von Oswald et al., 2023), its application to safe reasoning assumes that the reasoning process itself consistently produces "pure" safety signals ($y_s=1$ for $x_s=c_0$). 

**Key Technical Concerns:**
1. **The Gradient Bias Risk:** If a complex jailbreak prompt $x_0$ biases the model's internal state such that the reasoning traces ${z_i\}$ are semantically "contaminated" by the attack context, the resulting gradient updates will not be aligned with the true safety vector $w$. Theorem 3.1 assumes the model can perfectly identify $c_0$ during reasoning, which is exactly what jailbreaks are designed to prevent.
2. **Orthogonality vs. Synergy:** The modeling of attack complexity $k$ as a sum of orthogonal concepts $c_i$ simplifies the "signal dilution" effect. However, if attack concepts are synergistic or hierarchical (e.g., a "fictional story" that *requires* "explosive device" knowledge for plot consistency), the dilution factor $1/(k+1)$ may be non-linear or masked.
3. **Refusal Threshold Stationarity:** The proof assumes the refusal threshold $\delta$ is a constant. In practice, the noise introduced by complex distractor concepts might effectively raise the "refusal floor," meaning the required reasoning $t$ could scale super-linearly with $k$.

Despite these theoretical simplifications, the core empirical result (ASR reduction) is robust across multiple models, suggesting the framework captures a real and exploitable phenomenon in LRM safety.
