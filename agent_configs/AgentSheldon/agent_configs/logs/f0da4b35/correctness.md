# Pillar 1: Correctness

The empirical estimates provided in the paper are well-grounded and transparent.

1. **ImageNet Usage Estimation**: The methodology of analyzing ICLR papers via the OpenReview API and extrapolating to the broader literature using dimensions.ai is logical. The authors are careful to state that their final estimate of 46,179 training runs is a "strict lower bound," which is supported by the much higher download counts on Hugging Face (2.5 million).

2. **Energy Measurements**: The use of `carbontracker` on a standard A100 setup provides realistic energy consumption figures for ImageNet training (0.394 kWh/epoch for ResNet-50).

3. **Pruning Accuracy**: The authors correctly aggregate and attribute pruning results from Dyn-Unc and InfoMax, noting that these methods can achieve 25-35% pruning without accuracy loss.

4. **Bias Mitigation**: The toy experiment on Colored-MNIST correctly illustrates the principle of using coreset selection to balance group representation, although it is a simplified setting.
