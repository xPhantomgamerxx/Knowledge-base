---
title: "WB-WAM: Heterogeneous Body-Hand Pre-training for Humanoid Loco-Manipulation"
date: 2026-09-28
topic: Humanoid
tags: [humanoid, world-action-model, whole-body-control, pretraining]
source: https://arxiv.org/abs/2609.34199
venue: "arXiv"
---

## Summary

WB-WAM is a World Action Model incorporating explicit whole-body action supervision into generative video pretraining. A shared 72-dimensional physical action space (body joint references, root motion, articulated hand states) integrates heterogeneous annotation sources, enabling joint video-and-action learning from 1,880.2 hours of partially annotated video and motion data. Priors are refined through PICO mid-training and adapted to robot tasks with auxiliary forward-kinematics supervision, using retargeted egocentric human demonstrations and robot trajectories. Reaches 81.9% on HumanoidArena in simulation and 84.0% mean success across five real-world tasks.

## Key Contributions

- A unified 72-D physical action space spanning body, root, and hand articulation, letting heterogeneous data sources (different annotation granularities/coverage) be jointly learned rather than requiring fully-annotated data throughout
- Scales pretraining to 1,880+ hours of partially-annotated video/motion data by design, rather than requiring that scale of fully-labeled data
- Forward-kinematics supervision as an auxiliary signal during robot-task adaptation, grounding the learned priors in physically consistent kinematics

## Strengths

- Explicitly handling "partially annotated" heterogeneous data at scale (rather than requiring uniform full annotation) is a practical and underappreciated design choice that unlocks much larger usable data pools
- Strong result consistency between simulation (81.9% HumanoidArena) and real-world (84.0% across five tasks) suggests the learned priors transfer reasonably well rather than overfitting to simulation
- The shared whole-body action space (body + root + hands) is a sensible unification given how interdependent these are during real loco-manipulation

## Weaknesses

- "Partially annotated" data inherently means some fraction of the training signal is missing or inferred — the paper doesn't detail how annotation sparsity affects which capabilities are learned best versus worst
- Five real-world tasks is a modest evaluation footprint relative to the scale of pretraining data (1,880+ hours), leaving a gap between pretraining scale and demonstrated downstream task diversity
- No direct comparison against other concurrent humanoid whole-body WAM pretraining efforts (e.g., HAF, DexWeave) on shared benchmarks

## Open Questions

- How does performance scale with pretraining data volume — is 1,880 hours near a plateau, or would substantially more partially-annotated data continue to help?
- Does the shared 72-D action space generalize to humanoid platforms with substantially different hand DoF or kinematic structure than those used in training?

## Significance

A solid contribution to the growing World Action Model line of work specifically targeting humanoid whole-body control, demonstrating that large-scale partially-annotated data can be productively leveraged rather than requiring fully-labeled datasets throughout.

## Links

- [Paper](https://arxiv.org/abs/2609.34199)
- [Project page](https://wb-wam.github.io/)
- [GitHub](https://github.com/WB-WaM/WB-WAM-Official)
