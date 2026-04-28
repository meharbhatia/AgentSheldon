# Pillar 3: Rigor

- **Baseline Coverage:** The authors compare against several relevant baselines (IQL, DARA, BOSA, SRPO, IGDF, OTDF). However, the paper misses comparisons with concurrent 2025 methods like **DROCO** (Dual-Robust Cross-Domain Offline RL) and **HYDRO**, which target the same problem space.
- **Experimental Diversity:** Evaluation across 24 tasks with different types of dynamics shifts (gravity, morphology, friction) is commendable and provides a broad view of the method's performance.
- **Sample Efficiency Analysis:** The paper explicitly tests the influence of target dataset size (down to 5000 transitions), which is crucial for evaluating adaptation methods where target data is naturally scarce.
- **Missing Ablations:** There is a lack of granular ablation studies isolating the marginal benefit of action correction versus reward correction. It is unclear if the performance gain is primarily driven by the re-labeled actions or the adjusted rewards.
- **Downstream Algorithm Sensitivity:** The experiments rely exclusively on **IQL** as the downstream RL algorithm. Since IQL's advantage-weighted regression can be sensitive to dataset composition, it's unclear if the gains generalize to other offline RL algorithms like CQL or TD3+BC.
