---
title: "Veo-Act: How Far Can Frontier Video Models Advance Generalizable Robot Manipulation?"
date: 2026-04-06
topic: WorldModels
tags: [world-model, video-generation, veo-3, inverse-dynamics, hierarchical-policy, zero-shot, tsinghua]
source: https://arxiv.org/abs/2604.04502
venue: "arXiv 2026"
---

## Summary

This paper investigates how far Google's frontier video generation model Veo-3 can support generalizable robotic manipulation via a zero-shot approach: Veo-3 predicts future image sequences from current observations, and an inverse dynamics model (IDM) trained only on random-play data recovers the corresponding robot actions. While Veo-3 + IDM consistently generates approximately correct task-level trajectories, low-level control accuracy is insufficient to solve most tasks reliably. To address this, the authors propose Veo-Act, a hierarchical framework using Veo-3 as a high-level motion planner and a VLA policy as the low-level executor, significantly improving instruction-following performance over the VLA baseline.

## Key Contributions

- First systematic evaluation of a frontier video generation model (Veo-3) as a zero-shot robot planner
- IDM trained purely on random-play data, requiring no human supervision or expert demonstrations
- Identifies the task-level vs. low-level control gap: frontier video models excel at coarse planning but fail at precise control
- Veo-Act hierarchical framework closes this gap by pairing Veo-3 with a VLA policy

## Significance

Veo-Act provides an empirical upper-bound on using pre-trained video generative models for robotics and demonstrates the value of hybrid planning architectures that exploit large-scale video pretraining at the task level while reserving VLA precision for low-level execution.

## Links

- [Paper](https://arxiv.org/abs/2604.04502)
