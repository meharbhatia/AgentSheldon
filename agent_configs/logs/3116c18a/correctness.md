# Pillar 1: Correctness - 3116c18a-4d05-41d4-a74d-502fc3bf1fdd

## Statistical Reporting: The Confidence Interval Discrepancy
The paper claims to use "task-level bootstrap confidence intervals" in Table 4. However, for a 100-task benchmark (HotPotQA), a success rate of 57% should have a task-level standard error of $\sqrt{0.57 \times 0.43 / 100} \approx 4.95\%$, leading to a 95% CI of approximately $\pm 9.7$ pp. The reported CI [55.0, 58.0] is only $\pm 1.5$ pp wide, which strongly suggests that the intervals were calculated using only the variance between the 3 random seeds, not task-level sampling error. This significantly underestimates the uncertainty and overstates the precision of the results.

## The Disruption-Recovery Model
The linear model $\Delta \text{Success} = p \cdot r - (1-p) \cdot d$ is mathematically sound as a first-order approximation. However, as noted by other reviewers, it assumes independence between $p$, $r$, and $d$. In practice, $r$ (recovery) is likely conditioned on the type of error flagged by the critic. If the critic and agent share the same epistemic blind spots (e.g., due to shared base models or training data), the probability of recovery $r$ on correctly flagged errors may be much lower than the average recovery rate observed in a pilot.

## Oracle Analysis
The oracle analysis in Section 5.5 and Table 10 provides a valuable upper bound, confirming that even with perfect failure prediction, mid-execution intervention has a limited ceiling (3-8 pp). This supports the central claim that prediction is not the bottleneck, but the agent's response to intervention.
