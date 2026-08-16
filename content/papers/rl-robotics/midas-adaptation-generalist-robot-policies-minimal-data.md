---
title: "MiDAS: Adaptation of Generalist Robot Policies with Minimal Data"
date: 2026-08-10
topic: RL-Robotics
tags: [rl-robotics, online-rl, few-shot-adaptation, residual-policy, vla-posttraining]
source: https://arxiv.org/abs/2608.11363
venue: "arXiv"
---

## Summary

MiDAS studies "minimal-data adaptation" — adapting a pretrained generalist VLA to a new task from as little as one demonstration plus autonomous online interaction. The recipe first anchors the pretrained VLA to the target task via behavior cloning on a single or few demonstrations, then improves it through value-based online RL applied to a residual policy layered on top of the frozen/anchored base. Evaluated on LIBERO and RoboCasa in simulation and on a real bimanual YAM robot platform.

## Key Contributions

- An offline (behavior cloning) to online (value-based residual RL) adaptation recipe requiring only one to a few demonstrations.
- A claimed first reliable demonstration of single-demonstration robot policy adaptation combined with autonomous online improvement.
- Validation on both simulated (LIBERO, RoboCasa) and real bimanual hardware.

## Strengths

- Extremely low data requirement (a single demonstration) is a meaningful practical result for real-world deployment.
- Residual policy parameterization preserves the pretrained VLA's competence while allowing targeted online correction.
- Validated on a real bimanual platform, not just simulation.

## Weaknesses

- Roughly 6 hours of real-world autonomous online interaction per task is still a nontrivial practical cost.
- The "single demonstration" framing may understate reliance on the underlying VLA's strong generalist pretraining.
- No public code repository was found at time of writing.

## Open Questions

- How sensitive is performance to the quality/representativeness of the single seed demonstration?
- Does the residual RL phase require task-specific reward engineering, or is it fully automated?
- How does MiDAS compare against other recent offline-to-online residual RL VLA methods (e.g. BORA) on shared benchmarks?

## Significance

A concrete step toward practical few-shot deployment of generalist VLA policies, combining minimal demonstration data with autonomous online RL refinement on real hardware.

## Links

- [Paper](https://arxiv.org/abs/2608.11363)
