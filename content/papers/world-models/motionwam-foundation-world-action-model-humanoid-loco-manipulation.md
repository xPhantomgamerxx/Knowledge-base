---
title: "MotionWAM: Towards Foundation World Action Models for Real-Time Humanoid Loco-Manipulation"
date: 2026-06-08
topic: WorldModels
tags: [world-action-model, humanoid, loco-manipulation, real-time, egocentric, whole-body-motion, Mondo-Robotics, HKUST]
source: https://arxiv.org/abs/2606.09215
venue: "arXiv 2606.09215"
---

## Summary

MotionWAM is a real-time World Action Model (WAM) for full-body humanoid loco-manipulation driven from a single egocentric camera. It replaces the conventional upper/lower body hierarchical split with a unified motion latent that conditions the policy on intermediate denoising features of a video world model, jointly predicting whole-body motion tokens covering locomotion, torso, foot interaction, and hand manipulation at 4.9 Hz — 7× faster than Cosmos Policy at comparable scale.

## Key Contributions

- Unified motion latent space: eliminates the upper/lower body split by predicting a single coherent whole-body motion token sequence covering all limbs simultaneously
- Video world model conditioning: policy acts on denoising features from an intermediate step of a video diffusion world model, providing rich future context without full video generation at inference
- 4.9 Hz real-time throughput versus 0.7 Hz for Cosmos Policy — 7× speedup at comparable parameter count
- 30%+ performance improvement over best VLA baselines on coordinated full-body tasks requiring leg-driven behaviors

## Significance

First WAM architecture to achieve real-time inference for humanoid whole-body control, removing the throughput barrier that made previous world-model-based policies impractical for dynamic full-body tasks.

## Links

- [Paper](https://arxiv.org/abs/2606.09215)
- [HTML](https://arxiv.org/html/2606.09215v1)
