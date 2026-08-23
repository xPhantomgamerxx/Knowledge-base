---
title: "Whole-Body Planning for Humanoids Navigating Confined Spaces via Self-Collision Avoidance References"
date: 2026-08-10
topic: Humanoid
tags: [humanoid, whole-body-control, motion-planning, residual-rl]
source: https://arxiv.org/abs/2608.10220
venue: "arXiv"
---

## Summary

Researchers at UT Austin propose a three-stage whole-body planner for humanoids moving through highly confined spaces: kinematic path planning over reachable rigid-body volumes, differentiable collision avoidance to build volume-informed guides for a full-order trajectory optimizer, and use of the optimized plans as references to train a residual RL policy for robust online execution.

## Key Contributions

- A three-stage pipeline that separates concerns cleanly: coarse kinematic feasibility, precise collision-aware trajectory optimization, and RL-based robustification for online execution — rather than attempting to solve confined-space navigation with a single monolithic method.
- Differentiable collision avoidance used specifically to build "volume-informed guides" for the trajectory optimizer, integrating geometric reasoning directly into the optimization objective rather than as a post-hoc filter.
- Uses the offline-optimized trajectories as references for residual RL training, combining the precision of trajectory optimization with the robustness of learned policies to online disturbances.

## Strengths

- Confined-space whole-body navigation (doorways, narrow corridors, cluttered environments) is a practically important and underexplored capability gap for humanoid deployment outside open factory floors.
- The staged design — offline optimization for precision, residual RL for online robustness — is a sensible hybrid that plays to the strengths of both classical trajectory optimization and learned control.

## Weaknesses

- Three-stage pipelines with distinct optimization and learning components introduce integration complexity and potential failure points at each stage boundary; the paper's handling of stage-to-stage error propagation is not detailed in available coverage.
- Full-order trajectory optimization can be computationally expensive; the paper's coverage doesn't clarify whether the confined-space planning runs online or is precomputed for known environments, which matters significantly for real deployment flexibility.

## Open Questions

- Does the approach generalize to previously unseen confined-space geometries at inference time, or does it require re-running the offline trajectory optimization stage per new environment?
- How does the residual RL policy handle confined-space scenarios where the offline reference trajectory itself becomes infeasible due to an unexpected obstacle?

## Significance

Addresses a specific and practically relevant whole-body control capability — navigating tight, real-world spaces — that is a precondition for humanoids to operate usefully outside purpose-built open industrial environments.

## Links

- [Paper](https://arxiv.org/abs/2608.10220)
