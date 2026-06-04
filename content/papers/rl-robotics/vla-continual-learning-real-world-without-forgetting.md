---
title: "Can VLA Models Learn from Real-World Data Continually without Forgetting?"
date: 2026-05-26
topic: RL-Robotics
tags: [continual-learning, catastrophic-forgetting, experience-replay, real-world, manipulation, benchmarking]
source: https://arxiv.org/abs/2605.26820
venue: "arXiv 2026"
---

## Summary

This paper presents the first systematic study of continual learning for VLA models under realistic real-world conditions. The authors construct a real-world continual learning dataset spanning four sequential manipulation tasks (rigid pick-and-place, contact-rich pressing, deformable folding, and multi-object long-horizon). The key finding is that VLA models suffer significant catastrophic forgetting when continually learning from heterogeneous real-world demonstrations. Experience replay is evaluated and key implementation factors governing its success are identified.

## Key Contributions

- First real-world continual learning dataset for VLAs covering four diverse sequential manipulation tasks
- Empirical demonstration of significant catastrophic forgetting in VLA models under realistic continual learning conditions
- Systematic evaluation of experience replay as a mitigation strategy with analysis of critical implementation factors
- Practical guidelines for deploying VLA models in settings where new skills must be acquired without resetting knowledge

## Significance

Closes a major gap between lab VLA evaluations (fixed task distributions) and real-world deployment (sequential skill acquisition), providing the community with rigorous empirical baselines and a reusable benchmark dataset.

## Links

- [Paper](https://arxiv.org/abs/2605.26820)
