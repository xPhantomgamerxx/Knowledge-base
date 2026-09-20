---
title: "GLoRI: Closed-Loop Whole-Body Tracking with Global-Local Reference Interaction for Humanoid Loco-Manipulation"
date: 2026-09-05
topic: Humanoid
tags: [whole-body-control, loco-manipulation, closed-loop-tracking, single-policy, unitree-g1]
source: https://arxiv.org/abs/2609.05994
venue: "arXiv"
---

## Summary

Presents a closed-loop whole-body tracking method combining global and local reference interaction signals, demonstrating autonomous loco-manipulation with a single unified policy on a real Unitree G1 interacting with diverse, previously unseen objects — extending beyond prior systems that rely primarily on teleoperation or handle only single-object interaction scenarios.

## Key Contributions

- Single-policy autonomous (non-teleoperated) loco-manipulation across diverse unseen objects on real hardware
- Global-local reference interaction design for closed-loop whole-body tracking that couples locomotion and manipulation reference signals
- Validated on physical Unitree G1 hardware, not simulation-only

## Strengths

- Real hardware validation with unseen objects is a stronger generalization test than most closed-loop tracking papers, which often stay in simulation or use known object sets
- Single-policy (rather than modular locomotion+manipulation stack) design simplifies deployment and reduces integration complexity

## Weaknesses

- "Diverse unseen objects" claims need clearer quantification (how diverse, how many, what failure modes) to assess true generalization breadth
- Global-local reference interaction mechanism's computational/latency cost for real-time closed-loop control isn't detailed in available summaries

## Open Questions

- How does the single-policy approach handle simultaneous locomotion perturbation and fine manipulation (e.g., being pushed while grasping)?
- Does the method require object-specific reference trajectories, or is reference generation itself autonomous/generalizable?

## Significance

Moving humanoid loco-manipulation from teleoperated or single-object demos toward autonomous, single-policy control over unseen objects on real hardware is a meaningful step toward deployable humanoid autonomy.

## Links

- [Paper](https://arxiv.org/abs/2609.05994)
