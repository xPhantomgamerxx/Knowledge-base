---
title: "ROVE: Unlocking Human Interventions for Humanoid Manipulation via Reinforcement Learning"
date: 2026-06-15
topic: RL-Robotics
tags: [humanoid, human-in-the-loop, VLA-post-training, optimistic-value-estimation, whole-body, dexterous]
source: https://arxiv.org/abs/2606.17011
venue: "arXiv 2026"
---

## Summary

ROVE is a Reinforcement Learning framework with Optimistic Value Estimation for post-training humanoid VLA models using imperfect human interventions. It builds a human-in-the-loop data collection pipeline that supports whole-body and dexterous-hand intervention, and introduces a state-value learning recipe that combines robot rollouts, human intervention trajectories, and human experience videos to produce robust advantage signals even from suboptimal demonstrations.

## Key Contributions

- Human-in-the-loop pipeline for humanoid manipulation supporting whole-body and dexterous-hand interventions
- Optimistic Value Estimation (OVE) to extract reliable advantage estimates from mixed-quality human trajectories
- State-value learning that fuses robot rollouts, human interventions, and experience videos for richer reward signal
- Validated on real-world humanoid manipulation tasks including novel objects and long-horizon sequences

## Significance

Enables humanoid VLAs to leverage imperfect human corrections — a practically abundant signal — through RL, overcoming the challenge that standard imitation learning from suboptimal interventions causes distribution collapse.

## Links

- [Paper](https://arxiv.org/abs/2606.17011)
