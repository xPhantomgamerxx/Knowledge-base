---
title: "Learning More from Less: Reinforcement Learning from Hindsight (LfH)"
date: 2026-07-10
topic: RL-Robotics
tags: [vla-posttraining, hindsight-relabeling, sparse-reward, sample-efficiency, rl-fine-tuning]
source: https://arxiv.org/abs/2607.09042
venue: "arXiv"
---

## Summary

LfH brings hindsight relabeling to RL post-training of VLAs by having a VLM propose an alternate ("hindsight") instruction that a failed rollout actually achieved, then scoring and training on both the original and relabeled trajectories. This recovers learning signal from failures that would otherwise contribute nothing under sparse task-success rewards.

## Key Contributions

- A VLM relabels both the instruction and the reward for groups of failed rollouts, rather than discarding them as zero-reward signal
- Joint training on original-task rollouts plus hindsight-relabeled rollouts, applicable across different VLA backbones
- Demonstrates 5x sample-efficiency improvement on out-of-distribution LIBERO-PRO tasks and validates on a physical Franka FR3 robot with drawers and a two-level rack

## Strengths

- Directly attacks the sparse-reward cold-start problem that plagues RL post-training of VLAs, which is one of the field's most persistent practical obstacles
- Real hardware validation (not just simulation) strengthens the claim
- Reported to outperform a dense progress-reward baseline, suggesting the gains aren't just from denser reward alone but from the relabeling mechanism itself

## Weaknesses

- Relies on VLM relabeling quality; a poor or hallucinated hindsight instruction/reward could inject misleading gradient signal, and robustness to this failure mode isn't clear
- Needs a "group of failed rollouts" to relabel, which may still require a non-trivial base success rate or rollout budget before hindsight is useful
- Real-robot evaluation scope (single robot, specific manipulation tasks) is narrow relative to the simulation claims

## Open Questions

- How sensitive are the sample-efficiency gains to the choice/quality of the relabeling VLM?
- Does the method scale to long-horizon, multi-stage tasks where "what was actually achieved" is harder to define than in short manipulation primitives?

## Significance

Hindsight relabeling was a major idea in classical goal-conditioned RL (HER); porting it to VLA post-training under sparse task rewards is a natural and potentially impactful extension given how expensive real robot rollouts are.

## Links

- [Paper](https://arxiv.org/abs/2607.09042)
