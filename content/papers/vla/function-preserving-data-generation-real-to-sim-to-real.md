---
title: "Function-Preserving Data Generation for Zero-Shot Real-to-Sim-to-Real Manipulation"
date: 2026-09-16
topic: VLA
tags: [synthetic-data, real-to-sim-to-real, data-generation, contact-rich-manipulation, vla-posttraining]
source: https://arxiv.org/abs/2609.18293
venue: "arXiv"
---

## Summary

Proposes a function-preserving real-to-sim-to-real data generation framework that synthesizes demonstrations from reconstructed real-world assets with no teleoperated seed trajectory required. It specifically targets contact-rich tasks (insertion, assembly) where standard shape augmentation breaks geometric fit constraints.

## Key Contributions

- Identifies that standard shape-augmentation pipelines distort task-critical geometric interfaces, producing invalid contact relationships (fit mismatches, interpenetration)
- Proposes constraint-guided asset augmentation that preserves functional/contact geometry while diversifying object shape
- Generates synthetic demonstrations end-to-end from reconstructed assets with no teleoperated seed trajectory, targeting zero-shot real-to-sim-to-real transfer

## Strengths

- Directly targets a real, under-addressed failure mode of generic 3D data augmentation (geometric interface distortion) rather than generic visual domain randomization
- Removing the teleoperated-trajectory requirement could meaningfully lower the cost of scaling synthetic data for precision/contact-rich tasks specifically

## Weaknesses

- "Function-preserving" constraints likely require task-specific geometric annotations or priors, limiting scalability to arbitrary new tasks without manual specification of what geometry must be preserved
- With no teleoperated seed trajectories, action-label plausibility rests entirely on the trajectory optimizer/physics reasoning, a strong assumption for very high-precision insertion tasks

## Open Questions

- How well does policy performance trained purely on this synthetic data transfer to real contact-rich tasks compared to methods that still use a handful of real demonstrations?
- Does the approach generalize beyond rigid-object insertion/assembly to deformable or articulated contact-rich tasks?

## Significance

Adds a geometrically-principled alternative to the growing body of synthetic-data-for-VLA-training work, addressing a specific and previously under-scrutinized weakness (contact/interface distortion) in existing augmentation pipelines.

## Links

- [Paper](https://arxiv.org/abs/2609.18293)
