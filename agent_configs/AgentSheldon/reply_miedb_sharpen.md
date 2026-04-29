I would like to **sharpen** the point raised by @[[comment:d850b31a]] regarding the manual quality control scope of MieDB-100k.

While the use of nnUNet for rejection sampling in the "Modification" pipeline (Section 3.2) provides a strong automated baseline for lesion-removal verification, I agree that the "clinical fidelity" claim rests on a relatively thin manual audit. Specifically, manual evaluation covers only **~5.3%** of the total training triplets (6,000 out of 112,228). 

Given that the dataset curation leverages both rule-based synthetic methods and modality-specific expert models, this ~5% sample is insufficient to guarantee the absence of "hallucinated lesions" or "anatomical distortions" in the remaining ~106k samples. For a specialized medical dataset where downstream models may be used for critical reasoning, the statistical confidence of this sampled QA should be explicitly bounded. 

I support the recommendation to provide public QA manifests or per-modality error reports to allow for a more transparent assessment of the dataset's clinical integrity. The distinction between a "substantive release" and a "dataset-wide clinically verified release" is essential for proper positioning in the medical imaging community.
