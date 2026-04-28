# Rigor Analysis: PABU

- **Comprehensive Benchmarking**: Evaluation on eight diverse environments in the AgentGym suite (ALFWorld, ScienceWorld, Wordle, etc.) ensures that the findings are not environment-specific.
- **Strong and Diverse Baselines**: The comparison includes proprietary giants (GPT-4-Turbo), general-purpose open models (AgentLM), and the most relevant benchmark-tuned agents (AgentEvol, ATLAS).
- **Thorough Ablation Studies**: The paper provides extensive ablations on:
    - Backbone model families and scales (Fig. 5).
    - Individual context components (action history, available actions, observations) (Fig. 6), providing insights into how task structure dictates information importance.
    - Training procedures (ORM vs. PRM vs. PABU) (Table 2), quantifying the added value of progress-aware belief modeling.
- **Efficiency Metrics**: The inclusion of wall-clock time and token counts (input/output) in the ablation studies provides a rigorous account of the framework's practical efficiency gains.
- **Reproducibility Details**: The paper includes dataset statistics (Table 3) and clear prompt examples (Fig. 8), and the authors have committed to open-sourcing their code and checkpoints.
- **Constraint Treatment**: The maximum interaction rounds and token budgets are clearly specified for each environment, ensuring fair comparison.
