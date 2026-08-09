---
title: "DenseReward: Dense Reward Learning via Failure Synthesis for Robotic Manipulation"
date: 2026-07-14
topic: RL-Robotics
tags: [rl-robotics, reward-modeling, synthetic-data, vla-posttraining]
source: https://arxiv.org/abs/2607.13033
venue: "arXiv"
---

## Summary

DenseReward trains a dense vision-language reward model on 27,000 automatically synthesized success/failure trajectories, predicting per-timestep frame-level task-progress scores rather than sparse binary success labels. It directly addresses the scarcity of diverse failure data needed for reliable RL reward supervision.

## Key Contributions

- An automatic failure-synthesis pipeline generating 27k success/failure trajectories, sidestepping the practical difficulty of collecting real failure demonstrations (which are often actively avoided during data collection).
- A dense, per-timestep reward signal (frame-level progress prediction) rather than sparse episode-terminal reward, which should provide substantially richer RL training signal.
- Explicit framing around the failure-data scarcity problem — most manipulation datasets are curated toward successful demonstrations, leaving reward models with poor calibration on what failure looks like.

## Strengths

- Failure data scarcity is a real and under-addressed problem in reward modeling — most datasets skew heavily toward successful trajectories, so a reward model that has actually seen diverse synthesized failures should be better calibrated to distinguish genuine progress from superficially similar but unproductive behavior.
- Dense, frame-level reward is generally far more useful for RL training than sparse terminal reward, since it provides gradient signal throughout the episode rather than only at completion.

## Weaknesses

- The quality of the entire approach depends on how realistic and diverse the synthesized failures actually are; automatically synthesized failures risk being either too easy to distinguish from success (limiting the reward model's discriminative training) or systematically unrepresentative of the failure modes real deployed policies actually exhibit.
- 27k trajectories, while substantial, is synthesized data — there's no indication from the available description of how well a reward model trained purely on synthetic failures transfers to scoring real robot rollouts with genuinely novel failure characteristics.

## Open Questions

- How are failures synthesized — through simulation, perturbation of successful trajectories, or generative-model-based augmentation — and how does the synthesis method affect failure realism?
- Does the dense reward model's per-timestep progress prediction hold up under adversarial or reward-hacking pressure once used to actually train an RL policy?
- How does DenseReward compare directly against other 2026 progress-reward-modeling approaches on the same manipulation task suite?

## Significance

A meaningful contribution to closing the failure-data gap in reward modeling for manipulation RL, complementing the broader push (alongside RARM and the Progress Reward Modeling survey also logged this week) toward denser, more reliable reward signals for robot policy training.

## Links

- [Paper](https://arxiv.org/abs/2607.13033)
