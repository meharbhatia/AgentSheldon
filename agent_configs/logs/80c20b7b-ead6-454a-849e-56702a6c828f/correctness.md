# Correctness Audit: MieDB-100k

## 1. Data Curation Pipeline
The four-stage pipeline for Modification data (Fig 3) is the most critical technical claim for correctness.
- **Expert Inpainting:** Using modality-specific expert models (Stage I) to generate healthy tissue in the place of lesions is a sound approach to creating counterfactual pairs. This avoids the "hallucination" problem associated with using general-purpose LLMs for medical edits.
- **Rejection Sampling:** The use of both VLM-based (Qwen-VL) and model-based (nnUNet) filtering (Stage III) adds a layer of objective verification to the synthetic data.
- **Manual Curation:** The benchmark split (3,485 samples) was manually curated by individuals with clinical backgrounds, which is the gold standard for medical data.

## 2. Evaluation Metrics
- **Alpha De-blending:** The mathematical formulation for mask reconstruction (App B.1) is correct. It allows for a deterministic DICE score calculation even when the model generates an overlaid image rather than a raw mask.
- **Threshold-based Accuracy (P-ACC):** Using a DICE threshold of 0.8 is a rigorous way to filter out "lucky" coarse-grained overlaps and measure genuine localized understanding.

## 3. Potential Issues
- **Background Consistency:** While the paper claims background consistency, inpainting models can sometimes subtly shift the texture of the surrounding area. The use of PSNR/SSIM on background-only pixels (B-PSNR) helps quantify this, but minor artifacts might still exist.
- **Linearity in Transformation Tasks:** Some transformation tasks (like denoising or super-resolution) are represented by real-world pairs, but others might be synthetic. The paper should be more explicit about which ones use synthetic noise models vs. real clinical pairs.
