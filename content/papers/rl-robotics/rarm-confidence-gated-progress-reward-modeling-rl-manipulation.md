---
title: "RARM: Confidence-Gated Progress Reward Modeling for RL in Manipulation"
date: 2026-06-24
topic: RL-Robotics
tags: [rl-robotics, reward-modeling, single-demonstration]
source: https://arxiv.org/abs/2606.22027
venue: "arXiv"
---

## Summary

RARM derives a reward model from a single successful demonstration, localizing rollout progress along the reference trajectory via self-supervised contrastive learning, and only rewards confident forward progress — avoiding false-positive rewards without needing task-specific supervision, subtask labels, or explicit failure data.

## Key Contributions

- A reward function learned from just one demonstration, substantially lowering the demonstration burden relative to methods requiring many labeled trajectories or extensive failure data.
- A confidence-gating mechanism that withholds reward unless progress is confidently detected, directly targeting reward hacking / false-positive reward exploitation, a persistent problem in learned reward models.
- Self-supervised contrastive localization of rollout progress against the single reference, avoiding manual subtask-boundary annotation.

## Strengths

- Reducing the demonstration requirement to a single successful trajectory is an aggressive and practically valuable claim if it holds — most reward-learning methods require either many demonstrations or explicit negative/failure examples, both of which are costly to collect.
- Explicitly gating reward by confidence is a reasonable mitigation against the classic failure mode where an RL agent discovers actions that fool a learned reward model into predicting progress that isn't real.

## Weaknesses

- A reward model derived from a single demonstration inherently has very limited coverage of the state space; task variations, distractors, or execution styles not resembling the single reference trajectory may receive poorly calibrated (over- or under-confident) reward signals.
- Confidence gating trades off reward density for reliability — overly conservative gating could starve the RL agent of learning signal in early training when few rollouts confidently match the reference progression, potentially slowing convergence.

## Open Questions

- How robust is single-demonstration reward modeling to demonstrations that are suboptimal or stylistically atypical for the task?
- What is the actual RL sample efficiency/convergence speed trade-off introduced by confidence gating, compared to a denser but less reliable reward signal?
- How does RARM compare against the vault's other recently logged progress-reward approaches (e.g., DenseReward, SARM2) on shared manipulation benchmarks?

## Significance

A data-efficient contribution to progress-based reward modeling for manipulation RL, directly relevant to lowering the demonstration/supervision cost of deploying RL fine-tuning for robot policies — a recurring theme across this quarter's RL-robotics literature.

## Links

- [Paper](https://arxiv.org/abs/2606.22027)
