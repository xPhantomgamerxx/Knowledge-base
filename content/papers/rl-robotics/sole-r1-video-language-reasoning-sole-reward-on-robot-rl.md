---
title: "SOLE-R1: Video-Language Reasoning as the Sole Reward for On-Robot Reinforcement Learning"
date: 2026-03-28
topic: RL-Robotics
tags: [reward-model, video-language, chain-of-thought, online-RL, zero-shot, dense-reward, manipulation]
source: https://arxiv.org/abs/2603.28730
venue: "arXiv 2026"
---

## Summary

SOLE-R1 (Self-Observing LEarner) is a video-language reasoning model designed as the sole reward signal for on-robot online RL. Given only raw video observations and a natural-language goal, SOLE-R1 performs per-timestep spatiotemporal chain-of-thought reasoning and produces dense estimates of task progress used directly as rewards, enabling zero-shot online RL from random initialization without ground-truth rewards, success indicators, demonstrations, or task-specific tuning.

## Key Contributions

- Spatiotemporal chain-of-thought (CoT) reasoning over raw video for per-timestep dense progress estimation
- Large-scale video trajectory and reasoning synthesis pipeline generating temporally grounded CoT traces aligned with continuous progress supervision
- Zero-shot online RL on previously unseen manipulation tasks across 40-task benchmark
- Outperforms strong baseline reward models without any task-specific reward engineering

## Significance

Demonstrates that a single video-language reasoning model can replace task-specific reward engineering entirely, making online RL accessible for novel robot tasks with zero human reward specification — a key step toward autonomous robot skill acquisition.

## Links

- [Paper](https://arxiv.org/abs/2603.28730)
