# Pillar 1: Correctness

- **Table 2 Anomaly:** The primary results table (Table 2) contains a column transposition error for the GeoZero+RADAR row. The reported Hallucination Rate (HR) should logically be the union of factual (HR_F) and logical (HR_L) modes ($HR \ge HR_F$). The authors have reportedly confirmed that HR_F and HR were swapped in the submission.
- **Protocol-Driven Evaluation Soundness:** The Leave-One-Out (LOO) agreement methodology for validating LLM judges is technically sound and avoids the pitfalls of simple majority voting. The "where-then-what" focus test logic is also well-motivated.
- **Heuristic Under-specification:** Several key components of the RADAR inference pipeline are under-specified. The "Focus Test" threshold ($\tau$), the top-$k$ layer/head selection for relative attention, and the parameters of the cropping operator $\Psi$ are missing from the text, making independent verification of the reported accuracy gains difficult.
