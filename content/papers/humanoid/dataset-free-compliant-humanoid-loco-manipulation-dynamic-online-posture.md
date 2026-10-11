---
title: "Dataset-Free Compliant Humanoid Loco-Manipulation with Dynamic Online Posture"
date: 2026-10-05
topic: Humanoid
tags: [humanoid, robotics, loco-manipulation, whole-body-control, compliance, sim-to-real]
source: https://arxiv.org/abs/2610.05678
venue: "arXiv"
---

## Summary

This paper (system name OCLO) proposes a humanoid whole-body controller that needs no human motion-capture dataset at all: given only two hand targets, it generates pelvis height and torso orientation online via an analytic reachability prior refined by sampling, and converts hand-applied forces into compliant displacements through a spring-damper model so the legs, waist, and pelvis yield under disturbance instead of losing balance.

## Key Contributions

- A dataset-free posture-generation pipeline: an analytic reachability prior followed by task-agnostic cost-based sampling to set pelvis height and torso orientation online, with no reference-motion dataset required.
- A compliance mechanism that maps hand-force disturbances into reference displacements via a spring-damper model, propagating compliance through legs/waist/pelvis rather than only the arms.
- Real-world deployment on a Unitree G1 across seven loco-manipulation tasks including crouched walking and lifting a box from a low surface.
- Ablations showing the reachability prior raises reference-acquisition success from 37.8% to 77.8%, and that compliance training prevents balance loss under disturbance where non-compliant ablations fail.

## Strengths

- Eliminates the dependence on human motion-capture datasets that most whole-body loco-manipulation controllers require, which could substantially lower the barrier to deploying such controllers on new embodiments.
- Reports a clear, large ablation effect (37.8% → 77.8%) isolating the specific contribution of the reachability prior.
- Compliance-under-load is validated directly against disturbances that break non-compliant baselines, giving a concrete safety/robustness comparison rather than just task success rate.

## Weaknesses

- Only two hand targets as input is a fairly constrained task specification; it's unclear how this scales to tasks needing finer end-effector orientation or multi-contact control beyond hands.
- Evaluated on a single platform (Unitree G1) and a modest task set (seven tasks); breadth of generalization across object shapes/weights is not established.
- The task-agnostic sampling-based refinement step may not scale well computationally to more complex scenes or tighter real-time constraints.

## Open Questions

- How does the dataset-free approach compare quantitatively (not just qualitatively) to mocap-driven whole-body controllers on the same tasks?
- Can the reachability-prior-plus-sampling posture generation extend to full dual-arm bimanual coordination rather than independent hand targets?
- How robust is the compliance model to unexpected, multi-directional, or sustained forces beyond the push tests reported?

## Significance

Removing the human-motion-data dependency from whole-body humanoid control, while still demonstrating compliant real-world behavior under disturbance, is a meaningful step toward more easily deployable loco-manipulation controllers that don't require expensive mocap pipelines for every new embodiment or task.

## Links

- [Paper](https://arxiv.org/abs/2610.05678)
