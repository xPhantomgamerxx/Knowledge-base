---
title: "HANDOFF: Humanoid Agentic Task-Space Whole-Body Control via Distilled Complementary Teachers"
date: 2026-06-04
topic: Humanoid
tags: [humanoid, whole-body-control, distillation, mixture-of-experts, task-space-interface]
source: https://arxiv.org/abs/2606.06493
venue: "arXiv"
---

## Summary

HANDOFF is a single humanoid whole-body controller built around a compact 10-D task-space interface, designed so that high-level planners (including LLM/agentic planners) can drive loco-manipulation without emitting full joint-space references. It is trained via multi-teacher KL distillation of three complementary specialists — whole-body motion tracking, locomotion, and fall-recovery — into a mixture-of-experts student under a context-conditioned gating scheme.

## Key Contributions

- A 10-D task-space action interface deliberately small enough for diverse planners (scripted, learned, or LLM-based) to drive, yet expressive enough to encode loco-manipulation behaviors.
- A mixture-of-experts distillation scheme that reconciles conflicting teacher priors: the body slice follows a velocity-gated blend of whole-body-tracking and locomotion teachers, the arm slice anchors to the WBC teacher, and a recovery-masked KL term routes to a fall-recovery expert.
- Empirical demonstration that naive single-teacher distillation fails to reconcile expressive posture priors (from a motion-tracking teacher) with accurate velocity tracking (from a locomotion teacher), motivating the context-gated MoE design.
- Real-world deployment on Unitree G1 matching state-of-the-art velocity tracking while offering one of the largest reported robust manipulation workspaces for a single controller.

## Strengths

- Directly targets a real pain point in humanoid autonomy stacks: the mismatch between what planners want to emit (task-space goals) and what low-level controllers need (joint torques/positions), rather than adding yet another end-to-end policy.
- The three-teacher decomposition (tracking, locomotion, fall-recovery) is a sensible task partition that mirrors how humanoid failure modes actually cluster in practice.
- Validated on real hardware (Unitree G1) rather than simulation-only, with a concrete, comparable metric (velocity tracking) against prior state of the art.

## Weaknesses

- The 10-D task-space interface, while planner-friendly, necessarily discards some expressiveness — it's unclear how it would scale to more dexterous, high-DoF manipulation (e.g., bimanual coordination with independent hand-level tasks) beyond what's demonstrated.
- Mixture-of-experts gating is context-conditioned but the paper doesn't detail failure behavior at gating boundaries (e.g., transitions between locomotion-dominant and manipulation-dominant regimes), a known weak point for MoE control architectures.
- Single-robot validation (Unitree G1); no evidence yet of transfer to platforms with substantially different morphology.

## Open Questions

- How robust is the context-conditioned gate to distribution shift — e.g., novel task combinations not represented in the three teachers' training distributions?
- Can the same distillation recipe extend to a fourth or fifth "teacher" (e.g., dexterous hand manipulation) without re-architecting the gating scheme?
- How does the 10-D interface compare against direct VLA-style action generation in terms of sample efficiency for downstream task learning?

## Significance

Addresses the interface problem between high-level (agentic/LLM) planning and low-level whole-body control — a structural bottleneck that is often glossed over in papers focused purely on either planning or control, making this a useful building block for more agentic humanoid systems.

## Links

- [Paper](https://arxiv.org/abs/2606.06493)
- [Project Page](https://lzyang2000.github.io/HANDOFF/)
