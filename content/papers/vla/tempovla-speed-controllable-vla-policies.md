---
title: "TempoVLA: Learning Speed-Controllable Vision-Language-Action Policies"
date: 2026-06-04
topic: VLA
tags: [vla, speed-control, trajectory-augmentation, manipulation, execution-speed]
source: https://arxiv.org/abs/2606.06491
venue: "arXiv 2606.06491"
---

## Summary

TempoVLA introduces explicit execution-speed control into Vision-Language-Action models. Real manipulation alternates between fast transit phases and slow, precise contact stages, yet standard VLAs inherit a single fixed speed from demonstrations. TempoVLA conditions the policy on a target speed token, enabling the same model to adapt its pace on demand.

## Key Contributions

- Variable-Speed Trajectory Augmentation (VSTA): re-times existing demonstrations to any target speed by merging or splitting action steps while preserving motion semantics, expanding training data across the speed spectrum
- Speed-conditioning mechanism that feeds an explicit speed signal into the VLA backbone so the model generates actions whose magnitude governs execution rate
- Demonstrated on multiple manipulation benchmarks, outperforming fixed-speed baselines in both task success and cycle time

## Significance

First VLA to decouple task competence from execution speed, enabling adaptive pacing strategies (e.g., slow during grasp, fast during transit) from a single policy — a practical step toward deployment-ready manipulation systems.

## Links

- [Paper](https://arxiv.org/abs/2606.06491)
- [HTML](https://arxiv.org/html/2606.06491v1)
