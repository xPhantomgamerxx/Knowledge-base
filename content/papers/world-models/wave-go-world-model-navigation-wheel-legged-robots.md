---
title: "WAVE-Go: World-Model Navigation with Adaptive Execution for Wheel-Legged Robots"
date: 2026-09-15
topic: WorldModels
tags: [navigation, wheel-legged-robots, adaptive-execution, image-goal-navigation]
source: https://arxiv.org/abs/2609.18193
venue: "arXiv"
---

## Summary

An image-goal navigation framework that separates world-model action-sequence prediction from an interruptible executor, which adaptively truncates and replans commands under an estimated cumulative-failure-risk budget when new observations invalidate the current plan.

## Key Contributions

- A conditional-risk formulation for selecting how much of a predicted action prefix to execute before replanning, instead of running full open-loop rollouts from the world model
- Explicit clearance/stability/task-evidence checks gating posture and locomotion-mode transitions, a wheel-legged-specific concern
- Gains over the strongest baseline on in-distribution (74.1%, +4.7pp) and dynamic out-of-distribution (63.3%, +7.7pp) navigation success, plus fewer collisions (4.4 to 2.9 per 100m)

## Strengths

- Addresses a real gap: most navigation world-model papers assume a predicted plan stays valid until the next full replan; this "how much of the plan to trust" framing is generalizable
- Applies world-model navigation to wheel-legged robots specifically, an embodiment with underexplored mode-switching dynamics relative to the heavily-studied quadruped/humanoid literature
- Reports both success-rate and safety (collision) metrics, not just task completion

## Weaknesses

- Gains are moderate in absolute terms; sensitivity/tuning of the risk-budget hyperparameter is unclear
- Evaluated on one wheel-legged platform; transfer of the adaptive-execution wrapper to other locomotion embodiments is untested

## Open Questions

- How is the conditional-risk budget calibrated for new environments without extensive tuning?
- Would this adaptive-execution wrapper improve any world-model navigation policy, or is it tailored to this specific model's prediction characteristics?

## Significance

A practical systems contribution pairing world-model foresight with uncertainty-aware, interruptible execution — relevant beyond wheel-legged robots to any world-model-driven navigation stack operating in dynamic environments.

## Links

- [Paper](https://arxiv.org/abs/2609.18193)
