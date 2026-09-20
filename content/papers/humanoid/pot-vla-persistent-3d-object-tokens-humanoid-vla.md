---
title: "Closing the Loop in Humanoid VLA: Persistent 3D Object Tokens for Verifiable Loco-Manipulation"
date: 2026-07-20
topic: Humanoid
tags: [vla, object-centric-representation, verification, 3d-perception]
source: https://arxiv.org/abs/2607.18016
venue: "arXiv"
---

## Summary

Identifies "object-state divergence" — where the object state used to condition a whole-body action differs from the state used to verify whether the action succeeded — as a core failure mode in long-horizon humanoid loco-manipulation, and proposes Persistent Object Tokenization (POT), which maintains role-indexed 3D object records from RGB-D observations to both condition and verify VLA actions.

## Key Contributions

- Formalizes the object-state-divergence problem for long-horizon humanoid VLA execution across movement, contact, occlusion, and recovery
- POT: persistent, role-indexed 3D object memory that exposes active task roles, metric 3D locations, relation features, and uncertainty to a whole-body action expert
- POT-VLA instantiation that closes a perception-action-verification loop, using post-execution RGB-D refresh to check whether grounded geometric predicates (intended physical relations) were actually achieved
- Reports real-robot results on a Unitree G1: improves success from 39/80 to 71/80 over a matched direct GR00T-N1.7 baseline across eight real-world task families

## Strengths

- Directly targets a well-identified and underexplored failure mode (losing track of object identity/state through occlusion and contact) rather than proposing yet another generic architecture tweak
- Nearly doubling success rate (39/80 → 71/80) against a strong, named, matched baseline (GR00T-N1.7) is a meaningful and specific real-hardware comparison, not just a simulation ablation
- The "largest gains on tasks requiring maintained 3D relations" finding is a sensible, testable claim that supports the paper's core hypothesis rather than an unexplained blanket improvement

## Weaknesses

- Only eight real-world task families and an 80-trial total evaluation budget is a fairly small sample for statistically robust claims about generalization
- Reliance on RGB-D observations and geometric predicate verification may be brittle for deformable, transparent, or highly occluded objects not well captured by simple 3D tokens
- Unclear how POT's persistent memory scales computationally as task horizon and object count grow

## Open Questions

- How does POT-VLA perform on objects with ambiguous or changing geometry (deformable, articulated, liquid-containing)?
- What is the computational/latency overhead of maintaining and refreshing persistent object tokens during real-time whole-body control?
- Does the verification mechanism enable actual closed-loop recovery (re-attempting a failed relation), or only detection of failure?

## Significance

Addresses a specific, concrete weakness of current whole-body humanoid VLA policies — silent failure due to lost object state during long-horizon, contact-rich tasks — with a real-hardware improvement over a strong open baseline, directly relevant to reliability concerns raised across the broader "verification/self-correction for VLA" literature.

## Links

- [Paper](https://arxiv.org/abs/2607.18016)
