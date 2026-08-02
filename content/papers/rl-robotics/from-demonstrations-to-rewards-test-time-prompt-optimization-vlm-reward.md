---
title: "From Demonstrations to Rewards: Test-Time Prompt Optimization for VLM Reward Models"
date: 2026-06-01
topic: RL-Robotics
tags: [reinforcement-learning, reward-modeling, test-time-adaptation, vla-posttraining]
source: https://arxiv.org/abs/2606.00083
venue: "arXiv"
---

## Summary

Demo2Reward, by Christian Gumbsch and collaborators (including researchers at the University of Amsterdam), addresses a known weakness of using pretrained VLMs as zero-shot reward models for robot RL: without careful prompt engineering, VLM rewards produce false positives that badly degrade downstream policy learning. Instead of hand-engineering prompts, Demo2Reward is a test-time adaptation technique that optimizes the reward model's language instruction using only a handful (3-10) of expert demonstration trajectories — the same small demonstration sets robotics practitioners already collect to bootstrap policy learning — with no additional model training or extra compute needed during policy learning itself.

## Key Contributions

- Identifies false-positive reward predictions from prompt-sensitive zero/few-shot VLM reward models as a major, underexamined bottleneck for downstream RL policy quality
- Demo2Reward: a test-time prompt-optimization procedure that tunes the reward model's language instruction using a small set of expert demonstrations (3-10 trajectories) that are typically already available for bootstrapping policy learning, rather than requiring a separately-collected calibration set
- Explicitly optimizes to reduce false positives while preserving true positives, rather than treating reward calibration as a generic accuracy-maximization problem
- Requires no additional model training or extra compute at policy-learning time — the adaptation happens once, at reward-model configuration time, reusing data the practitioner already needs to collect
- Shown to consistently outperform existing zero- and few-shot VLM reward-model baselines across multiple simulated robotic tasks and policy backbones, and to transfer to at least one real-world robotic learning scenario without hand-engineering a reward function

## Strengths

- Recognizes and exploits a genuinely useful synergy: the small demonstration sets already collected for policy bootstrapping can double as reward-model calibration data, avoiding extra data-collection burden
- The "reduce false positives while preserving true positives" framing is a more precise and RL-relevant objective than generic reward-accuracy metrics, since false-positive reward signal is specifically what causes reward hacking and policy degradation in downstream RL
- No added training or compute cost during policy learning is a meaningful practical advantage over approaches that require fine-tuning the VLM reward model itself
- Demonstrated across multiple policy backbones and both simulated and at least one real-world setting, suggesting the method isn't narrowly overfit to one architecture

## Weaknesses

- The approach still depends on having a small set of expert demonstrations available; in settings where even a handful of good demonstrations are hard to collect (e.g., truly novel or unsafe tasks), the method loses its main advantage over prompt engineering
- Test-time prompt optimization with 3-10 trajectories is inherently a low-data calibration regime; robustness to which specific demonstrations are chosen (i.e., variance across demonstration subsets) isn't clear from available summaries
- "Real-world robotic learning scenario" (singular, per search summaries) is a limited real-hardware validation for a method whose main selling point is practical deployability
- As a prompt-optimization method riding on top of a black-box VLM, its ceiling is still bounded by the underlying VLM's visual/semantic understanding — Demo2Reward reduces false positives from poor prompting but cannot fix cases where the VLM fundamentally cannot perceive task-relevant distinctions

## Open Questions

- How sensitive is the optimized prompt to the specific demonstrations used, and how many demonstrations are actually needed before returns diminish — is 3 enough, or is the 3-10 range doing most of the work at the top end?
- Does the method generalize across different base VLMs, or is the optimized-prompt approach tuned implicitly to quirks of one particular VLM's instruction-following behavior?
- How does Demo2Reward's reward quality compare directly (not just via downstream policy success) to reward models trained with a small amount of fine-tuning, to isolate whether prompt optimization alone is sufficient or fine-tuning would still add value?

## Significance

Demo2Reward is a practically-minded contribution to the "VLM-as-reward-model" line of work, showing that a low-cost, no-extra-training test-time adaptation step — reusing demonstrations robotics practitioners already collect — can meaningfully close the false-positive reward gap that has limited zero-shot VLM reward models, making reward-function-free RL more viable for real robot learning.

## Links

- [Paper](https://arxiv.org/abs/2606.00083)
