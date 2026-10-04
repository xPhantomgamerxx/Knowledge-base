---
title: "TANGO: Humanoid Navigation in Cluttered Environments with a Whole-Body Vision-Language-Action Model"
date: 2026-09-08
topic: Humanoid
tags: [humanoid, vla, navigation, whole-body-control, sim-to-real]
source: https://arxiv.org/abs/2609.09158
venue: "arXiv"
---

## Summary

TANGO treats humanoid navigation through clutter not as 2D path planning but as a whole-body control problem requiring continuous geometry-aware adaptation (arm placement, torso adjustment, gait modulation) for collision-free movement through complex 3D space. Given a language instruction and egocentric RGB, it directly predicts 29-DoF joint-space actions. Trained entirely in simulation via global path planning, kinematic whole-body motion generation, obstacle-aware motion editing, and RL-based tracking, it deploys zero-shot on a Unitree G1, navigating a 30-meter route through a cluttered real office with narrow passages and overhead/floor obstacles, with no real-world navigation training data.

## Key Contributions

- Reframes humanoid navigation as whole-body control rather than 2D path planning plus separate locomotion execution — explicitly modeling how arm/torso/gait must jointly adapt to clutter geometry
- An entirely-simulation training recipe (path planning + kinematic motion generation + obstacle-aware editing + RL tracking) that transfers zero-shot to real hardware with no real navigation data
- Demonstrates a genuinely long real-world traversal (30 meters) through narrow passages and mixed overhead/floor obstacles, not just short obstacle-avoidance snippets

## Strengths

- The whole-body reframing of navigation is conceptually right: a humanoid squeezing through clutter does need coordinated arm/torso/gait adjustment, not just a 2D footstep plan, and TANGO operationalizes this directly
- Zero-shot sim-to-real transfer with no real navigation training data, validated on a nontrivial 30-meter cluttered route, is a strong practical demonstration of the training recipe's robustness
- Directly predicting 29-DoF joint actions from language + RGB end-to-end (rather than a hierarchical planner-executor split) keeps the system simpler to deploy

## Weaknesses

- Entirely-simulation training means real-world clutter diversity (lighting, object materials, unexpected obstacle types) is necessarily bounded by what the simulation and motion-editing pipeline can represent — the paper's single office-environment validation doesn't probe this boundary extensively
- 29-DoF joint prediction at the whole-body level is a large action space for a reactive policy; latency and failure-recovery behavior under sudden obstacle changes isn't detailed
- Single robot platform (Unitree G1) and a single real test environment is a narrow validation given the generality implied by "humanoid navigation in cluttered environments"

## Open Questions

- How does TANGO handle dynamic obstacles (moving people, objects) rather than the presumably static clutter in the validated office environment?
- Does the whole-body action formulation generalize to humanoids with substantially different kinematic proportions or DoF counts than the G1?

## Significance

A clear conceptual advance in treating humanoid navigation as a whole-body control problem, with a notably strong zero-real-data sim-to-real result that's directly relevant to deploying humanoids in real, unstructured indoor environments.

## Links

- [Paper](https://arxiv.org/abs/2609.09158)
