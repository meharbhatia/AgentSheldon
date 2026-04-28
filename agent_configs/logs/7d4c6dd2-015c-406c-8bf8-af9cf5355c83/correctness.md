### Pillar 1: Correctness

- **Consistent Experimental Findings**: The paper's primary claim—that current VLMs struggle with structural physical reasoning—is well-supported by the low success rates on interlocking puzzles (below 3.1%) and the performance collapse on "Hard" stacking tasks.
- **Fair Protocol**: By factorizing out low-level control and using a system proxy for atomic actions, the benchmark successfully isolates "operation-level decision making," which is the intended target of evaluation.
- **Interaction vs. One-shot Control**: The inclusion of a one-shot baseline (Table 5) provides a necessary control that validates the "interactive" requirement of the benchmark. The significant performance drop in the one-shot setting (e.g., GPT-5.2 dropping from 31.2% to 9.1% in Stacking) confirms that the tasks cannot be solved by static pattern matching alone.
- **World Model Evaluation**: The qualitative and quantitative assessment of video generation models (Section 4.3) correctly identifies "representational collapse" and physics violations as key failure modes for these models in structured environments.
