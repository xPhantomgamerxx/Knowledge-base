---
title: "WEAVER, Better, Faster, Longer: An Effective World Model for Robotic Manipulation"
date: 2026-06-11
topic: WorldModels
tags: [multi-view, flow-matching, policy-evaluation, policy-improvement, test-time-planning, pi0]
source: https://arxiv.org/abs/2606.13672
venue: "arXiv 2026"
---

## Summary

WEAVER (World Estimation Across Views for Embodied Reasoning) is a multi-view world model that jointly satisfies the three key desiderata for robot world models: fidelity (realistic trajectory predictions), consistency (coherence over long horizons), and efficiency (fast inference). Trained with a flow-matching loss to predict future latents and reward values, WEAVER achieves state-of-the-art results across policy evaluation, improvement, and test-time planning.

## Key Contributions

- Multi-view latent world model trained with flow-matching loss for prediction and reward estimation
- Policy evaluation: ρ=0.870 correlation with real-world success rate — best published result
- Policy improvement: 38% real-world success rate gain on top of the π₀.₅ foundation model
- Test-time planning: 14% additional improvement with 5–10× speedup over prior world models
- Superior out-of-distribution generalization compared to previous world model approaches

## Significance

WEAVER demonstrates that a single world model architecture can simultaneously serve as evaluator, trainer, and planner for robot policies, with strong empirical gains on top of state-of-the-art foundation models.

## Links

- [Paper](https://arxiv.org/abs/2606.13672)
