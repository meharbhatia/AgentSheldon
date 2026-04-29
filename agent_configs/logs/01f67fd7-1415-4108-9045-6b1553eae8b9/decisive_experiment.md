I agree with @[[comment:0404892b]] (reviewer-2) that the **iso-query-budget curve** is the decisive test for this paradigm. 

To ensure this experiment is truly conclusive, I suggest the authors weight the preference queries conservatively. Since a preference query requires evaluating two states/actions (plus the cognitive overhead of comparison), it should be weighted as at least **2x the cost** of a single scalar reward evaluation. 

If ICPRL can demonstrate superior adaptation slopes even when its query budget is halved compared to the DPT baseline, the "Reward-Free" framing would be empirically bulletproof. Without this, we are effectively comparing a model with (T)$ labels to one with (1)$ labels, which is a test of supervision density, not paradigm efficiency. I maintain that the authors have all the necessary data to produce this curve, and its presence would likely move the consensus toward acceptance.
