---
title: "FIERCE: From Generalist Robot Policies to Fast Specialists via Progress-Failure Feedback"
date: 2026-09-27
topic: RL-Robotics
tags: [rl-robotics, vla, online-rl, reward-modeling, vla-posttraining]
source: https://arxiv.org/abs/2609.18651
venue: "arXiv"
---

## Summary

FIERCE is a generalist-initialized RL framework that turns a broad VLA policy into a compact task specialist using a unified, task-adaptive progress-failure evaluator instead of manually engineered dense rewards or a dedicated simulator. The evaluator shares an observation-language representation between a progress head and an action-conditioned failure predictor, providing shaping and failure-risk signal that trains the specialist while alternating evaluator/policy updates on newly collected real-world experience.

## Key Contributions

- Removes the need for continued generalist action queries, a dedicated target-task simulator, or manually annotated dense rewards during specialist training — three common cost centers in generalist-to-specialist RL pipelines.
- A single evaluator architecture that jointly handles progress estimation and failure-risk prediction via shared representations, rather than training two separate reward/cost models.
- Only the compact specialist is retained at deployment, meaning the (presumably heavier) generalist and evaluator machinery is a training-time-only cost.

## Strengths

- Directly targets a practical deployment need: teams often want a fast, compact specialist for a narrow production task rather than paying inference cost for a full generalist VLA at every timestep.
- Avoiding manually annotated dense rewards addresses a real scalability bottleneck for RL fine-tuning across many different target tasks.
- The alternating evaluator/policy update scheme with fixed evaluator snapshots for shaping is a sensible design to avoid non-stationarity feedback loops between a constantly-moving evaluator and the policy it's shaping.

## Weaknesses

- Terminal rewards are described as "independently verified," implying some external verification signal is still needed per task, which is a residual cost not eliminated by the framework.
- No clear comparison given against directly fine-tuning the generalist itself (rather than distilling to a specialist) on wall-clock efficiency or final performance, which is the most natural baseline for this approach's central claim.
- "Fast specialist" claims depend heavily on how much real-world interaction is required to train the evaluator itself before it becomes a reliable shaping signal — an early-training cold-start cost that isn't obviously accounted for in the framing.

## Open Questions

- How much real-world data is needed to bootstrap the progress-failure evaluator before it produces useful shaping signal, relative to the specialist training itself?
- Does the resulting specialist retain any of the generalist's broader robustness, or does specialization strictly trade generality for speed/precision?
- How does this compare against reward-model approaches like large VLM-based reward generation on the same target tasks?

## Significance

Another entry in the fast-growing family of methods that use RL to convert broad, slow generalist VLA policies into fast, efficient specialists — a practically important pattern for any deployment where inference cost and task-specific precision matter more than open-ended generality.

## Links

- [Paper](https://arxiv.org/abs/2609.18651)
