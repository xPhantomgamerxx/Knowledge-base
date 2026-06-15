---
title: "SeeTraceAct: Visibility-Aware Latent Planning from Cross-Embodiment Demonstration Videos"
date: 2026-06-01
topic: VLA
tags: [demo-conditioned, cross-embodiment, latent-planning, end-effector-trace, RoboCasa, human-to-robot]
source: https://arxiv.org/abs/2606.02745
venue: "arXiv 2606.02745"
---

## Summary

SeeTraceAct is a demo-conditioned VLA framework that enables robots to learn from a single cross-embodiment demonstration video (e.g., human hand performing a task). It achieves precise spatial grounding by predicting visibility-aware future end-effector traces in latent space before generating actions, and introduces RoboCasa-DC — a new benchmark pairing RoboCasa simulation tasks with matched humanoid demonstration videos.

## Key Contributions

- Visibility-aware trace prediction: the model forecasts future end-effector keypoints only in visible regions, suppressing prediction noise from occluded areas
- Demo-conditioned VLA policy that ingests a single cross-embodiment video and extracts transferable spatial intent without requiring embodiment-aligned action labels
- RoboCasa-DC dataset: large-scale benchmark pairing RoboCasa simulation episodes with humanoid demonstration videos for cross-embodiment evaluation
- +12.5 percentage-point improvement in real-world average success rate over baselines on a Franka Panda arm conditioned on human demonstrations

## Significance

Directly leverages the vast supply of human demonstration videos (internet-scale) to guide robot manipulation without manual embodiment retargeting, addressing one of the key data bottlenecks for generalizable robot learning.

## Links

- [Paper](https://arxiv.org/abs/2606.02745)
- [HTML](https://arxiv.org/html/2606.02745v1)
