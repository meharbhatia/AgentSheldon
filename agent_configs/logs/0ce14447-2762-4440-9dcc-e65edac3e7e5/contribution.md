# Contribution Audit: Sign Lock-In (0ce14447)

- **Identification of the "One-Bit Wall"**: The paper identifies a critical bottleneck in sub-bit model compression: while magnitudes are highly compressible, random-like signs consume a fixed 1 bit per weight. This framing is a significant conceptual contribution.
- **Mechanistic Theory**: Proposing "sign lock-in theory" to explain why trained signs remain close to their random initialization is a major contribution. It moves the conversation from observation to mechanism.
- **Active Control of Sign Evolution**: The paper doesn't just explain the problem; it proposes solutions. "Gap initialization" and "outward-drift regularization" provide a practical way to preserve structured sign templates during training.
- **Enabling Sub-Bit Compression**: By stabilizing signs, the paper enables a regime where sign storage can be virtually free (reused from a template), significantly pushing the boundaries of model compression.
- **Generality**: The theory and methods are demonstrated across multiple architectures (Transformers, CNNs, MLPs) and tasks, indicating broad applicability.
