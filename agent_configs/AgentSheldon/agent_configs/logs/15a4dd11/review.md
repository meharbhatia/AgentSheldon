# Review: Conditionally Site-Independent Neural Evolution of Antibody Sequences

CoSiNE is a rigorous and well-motivated framework that successfully unifies neural sequence models with continuous-time Markov chains to model antibody affinity maturation. By conditioning site-specific rate matrices on the full sequence context, the model captures complex epistatic interactions while remaining computationally tractable for both likelihood estimation and sampling.

## Pillar 1: Correctness
The theoretical foundation of CoSiNE is sound. The proofs for the $O(t^2)$ approximation error and the exactness of the Gillespie sampling procedure are mathematically rigorous. The mutation-selection decomposition for zero-shot VEP is principled, leveraging the Thrifty model to effectively disentangle neutral mutation from selection. A minor concern is the admitted bias in rate estimation when training on long branches using a factorized objective, although the authors' synthetic experiments suggest that the resulting Gillespie sampling is still robust.

## Pillar 2: Contribution
This work makes a high-impact contribution by providing an evolutionary grounding for antibody sequence models. While marginal language models have dominated the field, CoSiNE demonstrates that modeling the *process* of affinity maturation provides a superior inductive bias for fitness prediction. The "Guided Gillespie" algorithm is a particularly valuable contribution, enabling target-specific antibody optimization without the need for labeled fine-tuning.

## Pillar 3: Rigor
The paper exhibits exceptional experimental rigor. The evaluation spans multiple DMS assays and includes a comprehensive set of baselines. The synthetic validation on a 64-state codon space is particularly commendable, as it isolates the effects of epistasis on estimation error. The categorical Jacobian analysis provides clear evidence that the model learns biologically plausible inter-chain dependencies.

## Pillar 4: Clarity
The manuscript is exceptionally clear and transparent. The authors do not shy away from negative results, such as the failure of SNR-weighting on the real antibody dataset, which adds to the credibility of the work. The distinction between "independent sites" and "conditionally site-independent" is well-articulated.

## Recommendation: Accept (Score: 8.5)
CoSiNE is a strong candidate for acceptance. It is a theoretically elegant and empirically robust model that addresses a critical gap in antibody engineering. The combination of evolutionary theory and deep learning is handled with high rigor, making this a high-quality contribution to the field.
