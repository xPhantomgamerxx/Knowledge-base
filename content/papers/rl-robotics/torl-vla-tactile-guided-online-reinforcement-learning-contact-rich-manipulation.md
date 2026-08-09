---
title: "TORL-VLA: Tactile Guided Online Reinforcement Learning for Contact-Rich Manipulation"
date: 2026-06-10
topic: RL-Robotics
tags: [rl-robotics, tactile, online-rl, contact-rich-manipulation, vla-posttraining]
source: https://arxiv.org/abs/2606.09337
venue: "arXiv"
---

## Summary

TORL-VLA is an online RL framework that refines a tactile/wrench-aware VLA's reference actions via a lightweight stage-specific actor-critic module conditioned on measured and predicted wrench feedback, enabling online adaptation to shifted contact conditions at deployment time. Real-robot results are reported on latch manipulation, coffee-cup placement, and egg handling.

## Key Contributions

- Online (deployment-time) RL refinement of tactile VLA actions, in contrast to the vault's already-logged TacCoRL, which uses offline simulation co-training rather than online adaptation.
- A lightweight, stage-specific actor-critic module conditioned on wrench (force/torque) feedback, keeping the online adaptation component small relative to the base VLA.
- Real-robot evaluation on tasks explicitly chosen for contact-rich, force-sensitive interaction (latch manipulation, cup placement, egg handling) — tasks where getting contact force wrong causes visible failure (breakage, drops, slips).

## Strengths

- Online adaptation to shifted contact conditions is directly relevant to real deployment, where surface friction, object compliance, and mechanical tolerances vary from what any offline training distribution captured — a lightweight actor-critic refinement layer is a reasonable way to close this gap without retraining the full VLA.
- Egg handling as an evaluation task is a genuinely demanding test of force calibration (too little force drops the egg, too much cracks it), giving a meaningfully hard real-world signal rather than a toy benchmark.

## Weaknesses

- Online RL at deployment time carries real safety and sample-efficiency risk on physical hardware — exploration noise from an online actor-critic module could produce damaging actions (e.g., excessive force) before it converges, and the paper's handling of this exploration-safety trade-off isn't described in available sources.
- The lightweight actor-critic module's capacity constrains how much it can actually correct; for base-VLA errors that are large or systematic rather than fine contact-force adjustments, online refinement alone may be insufficient.

## Open Questions

- What safety mechanisms (e.g., force limits, conservative exploration) are used to prevent damaging actions during online RL exploration on real hardware?
- How many online interaction steps are needed before the actor-critic module meaningfully improves over the base VLA's reference actions?
- How does TORL-VLA's online approach compare directly against TacCoRL's offline co-training approach on the same contact-rich task suite?

## Significance

A practically grounded contribution to online RL fine-tuning of tactile-aware VLAs, directly relevant to the digest's priority on RL fine-tuning of VLA policies, with real-robot validation on tasks that meaningfully stress-test force-sensitive manipulation.

## Links

- [Paper](https://arxiv.org/abs/2606.09337)
