---
title: "SARM2: Multi-Task Stage Aware Reward Modeling for Self Improving Robotic Manipulation"
date: 2026-06-09
topic: RL-Robotics
tags: [reward-modeling, stage-aware, mixture-of-experts, self-improvement, SPIRAL, long-horizon, on-robot-RL, VLA]
source: https://arxiv.org/abs/2606.10305
venue: "arXiv 2606.10305"
---

## Summary

SARM2 introduces a multi-task stage-aware reward model that combines an action-primitive-based stage estimator with a multi-gate Mixture-of-Experts (MMoE) value head to produce dense per-step rewards for long-horizon manipulation tasks. The stage estimator generalises across tasks through a shared action-primitive vocabulary, and its predicted primitive selects the corresponding MMoE gate. Built on SARM2, the authors present SPIRAL (Self-Policy Improvement via Reward-Aligned Learning), an on-policy real-robot RL framework that converts autonomous rollouts into a self-improving data flywheel without requiring additional human demonstrations.

## Key Contributions

- Action-primitive vocabulary shared across tasks: enables the stage estimator to transfer dense reward signals across diverse manipulation scenarios without per-task annotation
- MMoE value head gated by stage predictions: activates domain- and action-specific experts for accurate dense value estimation at each manipulation sub-stage
- SPIRAL: on-policy real-robot RL framework using SARM2's dense rewards to self-improve VLA policies through cheap autonomous rollouts
- Reduces dependence on costly high-quality demonstration data for fine-tuning long-horizon VLA policies

## Significance

SPIRAL closes the loop between reward modelling and policy improvement without human intervention, demonstrating a practical path to continuous autonomous self-improvement for VLA-based manipulation policies deployed on real hardware.

## Links

- [Paper](https://arxiv.org/abs/2606.10305)
- [HTML](https://arxiv.org/html/2606.10305)
