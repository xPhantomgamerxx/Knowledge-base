---
title: "ViLoMan: Learning Visual-Proprioceptive Whole-Body Loco-Manipulation Skills for Humanoid Robots"
date: 2026-09-16
topic: Humanoid
tags: [loco-manipulation, whole-body-control, teacher-student-distillation, sim-to-real, unitree-g1]
source: https://arxiv.org/abs/2609.19340
venue: "arXiv"
---

## Summary

Proposes a framework that converts partial kinematic demonstrations of human-object interactions into complete, physically executable robot trajectories, then uses teacher-student distillation to train a single unified policy mapping egocentric depth and proprioception directly to whole-body joint actions, deployed without reference motions or intermediate commands at test time.

## Key Contributions

- Pipeline for lifting partial human-object interaction demonstrations into physically valid, complete whole-body robot trajectories
- Teacher-student distillation approach producing a single deployable policy from egocentric depth + proprioception, without needing motion references or high-level command inputs at deployment
- Real-world validation on a Unitree G1 performing a full loco-manipulation task using only onboard sensing (no motion capture or external tracking)
- Demonstrates generalization across task variations and successful sim-to-real transfer

## Strengths

- Eliminating dependence on reference motions/intermediate commands at deployment is a meaningful practical simplification versus many whole-body control papers that still require a motion-tracking or goal-conditioning signal at test time
- Using only onboard depth + proprioception (no external mocap) is a stronger, more deployment-realistic sensing setup than papers relying on lab-only instrumentation
- Real hardware validation (Unitree G1) with reported sim-to-real transfer adds credibility beyond a purely simulated result

## Weaknesses

- "Completes the full task" language suggests validation on a specific task (or narrow task family); breadth of task/object generalization is unclear from available abstract-level material
- Converting "partial kinematic demonstrations" into "complete, physically executable" trajectories is a nontrivial inverse problem — the paper's reliability/failure rate for this conversion step isn't detailed in the search-derived summary
- No comparison numbers against strong recent whole-body baselines (e.g., OpenHLM, OmniContact) were found in available material, making relative performance hard to judge

## Open Questions

- How many distinct tasks/object categories were evaluated on real hardware, and what is the quantitative success rate?
- How robust is the human-demonstration-to-robot-trajectory conversion step to noisy or ambiguous human-object interaction data?
- Does the approach scale to bimanual dexterous manipulation, or is it primarily validated on coarser whole-body tasks?

## Significance

Adds to a fast-growing cluster of 2026 work attacking the same core problem — deployable, sensor-only (no mocap, no external tracking) whole-body humanoid control that generalizes beyond a single scripted motion — which is a prerequisite for humanoid robots operating outside instrumented lab environments.

## Links

- [Paper](https://arxiv.org/abs/2609.19340)
