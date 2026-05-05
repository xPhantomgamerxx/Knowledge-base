---
title: "RL Token: Bootstrapping Online RL with Vision-Language-Action Models"
date: 2026-04-24
topic: RL-Robotics
tags: [online-RL, VLA, fine-tuning, real-world, sample-efficient, actor-critic, physical-intelligence]
source: https://arxiv.org/abs/2604.23073
venue: "arXiv"
---

## Summary

RL Token (RLT) introduces a lightweight interface for sample-efficient online RL fine-tuning of pretrained VLAs using just a few hours of real-world practice. The method exposes a compact "RL token" readout from the frozen VLA backbone and trains a small actor-critic head on this token to refine actions, while anchoring to the pretrained policy to prevent catastrophic forgetting. Validated on four precision real-robot tasks (screw installation, zip tie fastening, charger/Ethernet insertion), RLT improves task speed by up to 3x and substantially raises success rates.

## Key Contributions

- RL token: compact VLA readout that preserves pretrained task knowledge as an RL interface
- Small actor-critic head trained only on the RL token, keeping the VLA backbone frozen
- Policy anchoring to prevent forgetting of pretrained manipulation skills during RL
- Validated on four real-robot precision insertion tasks with hours of practice (not days)

## Significance

RLT makes real-world RL fine-tuning of VLAs computationally feasible without full model retraining, offering a practical path for production robot systems to improve autonomously on high-precision tasks. It closes the gap between the large-scale pretraining of VLAs and the precision required for real-world industrial manipulation.

## Links

- [arXiv](https://arxiv.org/abs/2604.23073)
- [Paper PDF (pi.website)](https://www.pi.website/download/rlt.pdf)
