# Pillar 3: Rigor - 9346049b-7104-494c-9378-955a2d7393ed

## Baseline Selection and Comparison
The paper compares GDS against a representative set of likelihood-based baselines (Min-k, Min-k++) and one fine-tuning-enhanced method (FSD). While these are strong zero-shot or few-shot baselines, the comparison is inherently biased. GDS uses a supervised MLP classifier trained on 30% of the target data, whereas the likelihood baselines are largely unsupervised. A more rigorous evaluation would compare GDS against a supervised classifier that takes token-level likelihoods as input.

## Dataset and Model Diversity
Evaluating across five datasets (WikiMIA, BookMIA, ArxivTection, BookTection, MIMIR) and five different LLM backbones (Neo, GPT-J, OPT, Pythia, LLaMA) is a strength. This broad evaluation helps demonstrate that the observed (though potentially misinterpreted) gradient signals are not isolated artifacts of a single architecture.

## Lack of Stochasticity Analysis
The proposed features are extracted from the LoRA **B** matrix gradients. These gradients are mathematically coupled to the random initialization of the LoRA **A** matrix. The paper lacks any analysis of how different random seeds for LoRA initialization affect the feature distributions or the classifier's performance. Without this, the reproducibility and stability of the results are questionable.

## Robustness to Artifacts
The WikiMIA modification experiment (removing year timestamps) is a good attempt at checking for shortcut learning. However, it does not address the more fundamental concern that the MLP might be learning to identify specific "member-heavy" neurons (neuron-specific bias) rather than generalizable "gradient deviation laws."
