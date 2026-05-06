---
title: "H-WM: Robotic Task and Motion Planning Guided by Hierarchical World Model"
date: 2026-02-11
topic: WorldModels
tags: [hierarchical, task-and-motion-planning, logical-world-model, visual-world-model, long-horizon, VLA-guidance]
source: https://arxiv.org/abs/2602.11291
venue: "arXiv"
---

## Summary

H-WM proposes a two-level world model that integrates symbolic task planning with visual dynamics to address the limitations of single-modal world models in long-horizon manipulation. A high-level logical world model predicts state transitions in logical/symbolic space, providing structured task decomposition and long-horizon robustness. A low-level visual world model then grounds these logical states in visual observations, enabling precise execution via VLA control policies.

## Key Contributions

- Hierarchical World Model (H-WM): joint prediction of logical and visual state transitions across two levels
- High-level logical world model for symbolic long-horizon planning and robust task decomposition
- Low-level visual world model for grounding symbolic states in visual observations and guiding VLA policies
- Hierarchical intermediate outputs that mitigate error accumulation across extended task sequences
- Demonstrated generality across multiple VLA control policy architectures

## Significance

H-WM bridges the gap between classical TAMP and learned world models, enabling robust long-horizon robot control without requiring explicit symbolic state definitions at deployment time.

## Links

- [Paper](https://arxiv.org/abs/2602.11291)
