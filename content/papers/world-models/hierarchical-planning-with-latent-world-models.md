---
title: "Hierarchical Planning with Latent World Models"
date: 2026-04-03
topic: WorldModels
tags: [hierarchical-planning, latent-world-model, zero-shot, long-horizon, Meta-FAIR, VJEPA2, pick-and-place]
source: https://arxiv.org/abs/2604.03208
venue: "arXiv"
---

## Summary

This work (Meta FAIR / NYU / Mila / Brown) addresses the long-horizon failure mode of learned world models caused by compounding prediction errors and exponential search-space growth. A high-level planner uses a long-horizon world model to optimize macro-actions toward a goal; the first predicted latent state becomes a subgoal for a low-level planner that optimizes primitive actions with a short-horizon world model. Training on large offline, task-agnostic trajectories enables zero-shot deployment on downstream robotic tasks.

## Key Contributions

- Hierarchical World Model (HWM): high-level macro-action planner and low-level primitive-action planner at different temporal scales
- Zero-shot control on real-world non-greedy tasks (pick-and-place: 70% success vs. 0% for flat single-level world model)
- Training from unlabeled, task-agnostic offline trajectories without task-specific supervision
- Modular planning abstraction validated across VJEPA2-AC, PLDM, and DINO-WM latent world-model architectures

## Significance

HWM demonstrates that hierarchical temporal abstraction is a general and necessary component for deploying latent world models on real manipulation tasks requiring non-greedy planning.

## Links

- [Paper](https://arxiv.org/abs/2604.03208)
- [Project Page](https://kevinghst.github.io/HWM/)
