---
title: "PointZero: 3D Point Track Completion for Learning Transferable 3D Dynamics"
date: 2026-09-16
topic: WorldModels
tags: [3d-dynamics, point-tracking, robot-free-pretraining, action-conditioned-prediction, video-data]
source: https://arxiv.org/abs/2609.19142
venue: "arXiv"
---

## Summary

Proposes 3D point-track completion — predicting future 3D trajectories of sparse tracked points from a single RGB-D observation and partial tracks — as a robot-action-free pretraining objective for 3D dynamics, since both the supervision and conditioning signal (3D point tracks) are obtainable from any video via point tracking, not just labeled robot data.

## Key Contributions

- Robot-free, interaction-agnostic pretraining objective usable on web video via off-the-shelf point tracking, sidestepping the need for action-labeled data
- 2.9M-frame synthetic dataset spanning deformable, articulated, and rigid objects
- Demonstrates downstream transfer to both action-conditioned 3D dynamics prediction (outperforms on PGND benchmark) and imitation learning (outperforms/matches baselines on 6/7 manipulation tasks)

## Strengths

- Elegant unification: using point tracks as both label and conditioning signal makes the pretraining objective genuinely scalable to arbitrary video, not just robot demonstrations
- Validated on both a dedicated dynamics benchmark and real downstream manipulation tasks, not just a single proxy metric
- Open dataset, code, and checkpoints released

## Weaknesses

- Reliance on point-tracking quality as ground truth means errors/failures in the tracker propagate into pretraining supervision
- Synthetic dataset (2.9M frames) may not capture the full diversity of real-world contact dynamics, especially for deformables

## Open Questions

- How much does pretraining on real (vs. purely synthetic) point-tracked video improve downstream transfer?
- Does the objective scale favorably with web-video volume the way language/vision pretraining has?

## Significance

Offers a genuinely scalable, action-free path to 3D dynamics pretraining that could let world models and VLA action experts benefit from web-scale video without expensive action annotation.

## Links

- [Paper](https://arxiv.org/abs/2609.19142)
