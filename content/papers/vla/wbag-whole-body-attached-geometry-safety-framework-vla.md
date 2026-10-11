---
title: "WBAG: A Whole-Body and Attached-Geometry Safety Framework for Vision-Language-Action Manipulation"
date: 2026-10-01
topic: VLA
tags: [vla, safety, robotics]
source: https://arxiv.org/abs/2610.01083
venue: "arXiv"
---

## Summary

WBAG is a safety layer for VLA robot policies that protects the entire articulated robot body and any object currently grasped, rather than only checking the end-effector position, which is the common simplification in prior VLA safety work. On the SafeLIBERO benchmark it reports 97.38% aggregate scene safety and 59.38% safe success, described as the best among compared methods.

## Key Contributions

- A safety-checking formulation that explicitly models whole-body and attached-object geometry, not just the end effector.
- Evaluation on SafeLIBERO, a benchmark designed to jointly measure task success and safety violations.
- Comparison against existing VLA safety approaches with a reported improvement on both scene safety and safe-success metrics.

## Strengths

- Addresses a real gap: end-effector-only safety checks miss collisions from the robot's arm, body, or a long/awkward grasped object.
- Reports both a safety metric and a "safe success" metric jointly, avoiding the trap of only reporting collision avoidance while ignoring whether the task still gets done.

## Weaknesses

- Version history for the paper is inconsistent across sources (v1 vs. v2 dates), suggesting the work may still be actively revised.
- Evaluated only in the SafeLIBERO simulation benchmark in the available material; no real-robot safety validation is mentioned.
- Modeling attached-object geometry likely requires reasonably accurate object shape/pose estimation, whose own error could propagate into safety decisions.

## Open Questions

- How does WBAG perform when the attached object's geometry is partially occluded or poorly estimated?
- What is the computational overhead of whole-body/attached-geometry checking relative to end-effector-only methods, and is it compatible with real-time control rates?

## Significance

Part of a growing safety-for-VLA sub-field (alongside SafeVLA, VLSA/AEGIS, "A Safe Action Is Not Enough") that is moving past success-rate-only evaluation toward explicit, geometry-aware safety guarantees — an important step for any real-world deployment of VLA-controlled manipulators.

## Links

- [Paper](https://arxiv.org/abs/2610.01083)
