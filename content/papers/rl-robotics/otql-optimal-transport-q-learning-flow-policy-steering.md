---
title: "Optimal Transport Q-Learning for Flow Policy Steering and Acceleration (OTQL)"
date: 2026-07-07
topic: RL-Robotics
tags: [vla-posttraining, rl-fine-tuning, flow-matching, optimal-transport, sample-efficiency]
source: https://arxiv.org/abs/2607.06262
venue: "arXiv"
---

## Summary

OTQL fine-tunes and accelerates suboptimal flow/diffusion-based robot policies (including pretrained VLAs) using advantage-weighted conditional optimal-transport flow matching, achieving both higher success rates and fewer inference denoising steps from very small interaction budgets (50-60 episodes).

## Key Contributions

- Formulates RL post-training of flow policies as conditional OT flow matching weighted by learned advantages, avoiding the need for computationally expensive distillation
- Demonstrated on both single-task flow policies and a pretrained VLA, in simulation and on real robot tasks
- Reports raising single-task policy success from 36% to 86% and pretrained VLA success from 38% to 76%, while cutting inference steps per action by 70%

## Strengths

- Genuinely large reported improvements from a tiny interaction budget (50-60 episodes) is a strong sample-efficiency claim if it holds
- Jointly improves both success rate and inference speed, addressing two practical VLA deployment pain points (accuracy and latency) with one method
- Applies directly to a pretrained VLA, not just toy/single-task policies, which is the more industrially relevant setting

## Weaknesses

- Needs a learned Q-function, which introduces its own approximation error and training overhead the paper doesn't obviously eliminate, just relocates
- The dramatic success-rate jump (36→86%, 38→76%) invites scrutiny of task/baseline selection; unclear whether these gains generalize past the reported task set
- 50-60 episode budget is small but likely still assumes access to real-robot rollout infrastructure, which not every lab has

## Open Questions

- How does OTQL compare directly against other recent flow/diffusion RL fine-tuning approaches on the same tasks?
- Does the inference-step reduction hold up across different base VLA architectures and action-chunk sizes?

## Significance

Speed and sample-efficiency are the two biggest practical blockers to RL post-training of flow-matching VLA policies (π0-style models); a method claiming gains on both simultaneously, with a small real-robot budget, is directly relevant to closing that gap.

## Links

- [Paper](https://arxiv.org/abs/2607.06262)
