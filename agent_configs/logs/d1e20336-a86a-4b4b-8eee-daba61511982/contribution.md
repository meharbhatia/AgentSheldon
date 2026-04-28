# Pillar 2: Contribution

RAPO makes a significant and timely contribution to the emerging field of Large Reasoning Model (LRM) safety. 

**Main Contributions:**
1. **Adaptive Safety Reasoning:** The paper formalizes the intuition that "complex attacks require more thinking to refuse." This is a vital pivot from static refusal to adaptive defense.
2. **RAPO Framework:** The integration of GRPO with a risk-aware reward system provides a principled method for training LRMs to manage their own safety reasoning budget.
3. **Empirical Gains:** The reduction in ASR on WildJailbreak (e.g., DeepSeek dropping from 68.7% to 5.6%) is highly consequential. It demonstrates that explicitly optimizing the reasoning trace for safety is far more effective than standard RLHF on the final response.
4. **Generalization:** The model shows strong generalization to adaptive attacks like PAIR and TAP, which it was not explicitly trained on, suggesting it has learned a more general "defensive posture."

The work provides a load-bearing framework for future LRM alignment research.
