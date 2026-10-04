---
title: "Dissecting Advantage-Guided Post-Training for Vision-Language-Action Policies"
date: 2026-09-23
topic: VLA
tags: [vla, rl-post-training, advantage-estimation, vla-posttraining]
source: https://arxiv.org/abs/2609.28161
venue: "arXiv"
---

## Summary

A controlled ablation study of advantage-guided RL post-training for VLA policies, isolating which design choices (advantage construction, calibration, weighting) actually drive performance gains rather than proposing a wholly new algorithm. The authors identify a modular recipe — TD-style advantage construction + group-wise calibration + continuous advantage weighting — that improves mean task progress and success over SFT initialization by 0.42 and 0.63 respectively on four real bimanual tasks.

## Key Contributions

- Decouples three previously entangled design axes in advantage-guided VLA RL post-training and evaluates each independently
- Shows group-wise calibration of advantages matters more than the specific advantage-construction method
- Proposes continuous (rather than binary/thresholded) advantage weighting as a simple, broadly applicable improvement
- Validates the recipe on four real-world bimanual manipulation tasks, not just simulation

## Strengths

- Genuinely diagnostic rather than a "stack more tricks" paper — useful as a reference for anyone building an RL post-training pipeline
- Real-robot bimanual evaluation adds credibility over pure-simulation ablations common in this space
- The modular framing makes individual findings easy to port into other RL post-training stacks (e.g., GRPO variants)

## Weaknesses

- Four real tasks is a thin evidence base for claims about which design choices generalize across task types and embodiments
- No comparison against the latest GRPO-family methods (e.g., Prism-GRPO, Temporal GRPO) that address a related but distinct inefficiency (wasted same-outcome rollouts)
- Calibration recipe's sensitivity to reward sparsity/noise is not stress-tested

## Open Questions

- Does the "TD advantage + group calibration + continuous weighting" recipe hold up on higher-DoF dexterous or humanoid tasks?
- How does this recipe interact with online vs. offline RL settings, where advantage estimation noise characteristics differ substantially?

## Significance

As VLA post-training work increasingly reaches for RL, ablation studies like this are valuable for separating signal from noise in a rapidly accumulating pile of "novel" post-training tricks — a useful counterweight to purely additive progress claims.

## Links

- [Paper](https://arxiv.org/abs/2609.28161)
