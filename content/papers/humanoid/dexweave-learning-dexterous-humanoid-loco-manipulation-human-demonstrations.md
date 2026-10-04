---
title: "DexWeave: Learning Dexterous Humanoid Loco-Manipulation from Human Demonstrations"
date: 2026-09-28
topic: Humanoid
tags: [humanoid, dexterous-manipulation, motion-retargeting, whole-body-control]
source: https://arxiv.org/abs/2609.34724
venue: "arXiv"
---

## Summary

DexWeave connects interaction-consistent motion retargeting with anatomy-aware whole-body policy learning for humanoid loco-manipulation. A two-stage retargeting procedure first initializes body and hand motions with specialized solvers, then performs coupled refinement over the upper-body interaction chain while preserving lower-body support. The learned policies were deployed on a physical Unitree G1 with Inspire dexterous hands, demonstrating real-world dexterous whole-body loco-manipulation.

## Key Contributions

- A two-stage retargeting pipeline that separates initial per-part (body/hand) motion retargeting from a coupled refinement pass specifically over the interacting upper-body chain
- Preserves lower-body support/balance during the refinement stage rather than treating the whole body as a single undifferentiated retargeting problem
- Real hardware validation on Unitree G1 + Inspire hands, moving beyond simulation-only results common in this subfield

## Strengths

- The explicit preservation of lower-body support while refining upper-body interaction is a sensible and non-obvious design choice — naive whole-body retargeting often destabilizes balance when prioritizing hand/arm fidelity
- Real-world deployment on a standard, widely-used humanoid platform (Unitree G1) makes the result easier to compare against and build on for other groups
- Reports faster policy convergence and higher performance than MLP baselines, suggesting the structured two-stage approach has measurable value over naive end-to-end learning

## Weaknesses

- "Higher manipulation performance... than MLP baselines" is a fairly low bar for comparison; stronger baselines (e.g., other 2026 whole-body retargeting methods like WB-WAM) aren't directly compared
- Retargeting-based approaches inherit whatever biases exist in the human demonstration data (e.g., human hand kinematics not perfectly mapping to the Inspire hand's DoF), and the paper doesn't deeply quantify residual retargeting error
- Real-world evaluation scope (how many tasks, how many trials) isn't detailed in the available summary, making it hard to assess robustness

## Open Questions

- How does DexWeave's two-stage retargeting compare directly against concurrent 2026 whole-body pretraining approaches (e.g., WB-WAM) on shared tasks or platforms?
- Does the coupled refinement generalize to more dynamic (non-quasi-static) loco-manipulation tasks, or is it primarily validated on relatively controlled interactions?

## Significance

A solid contribution to the practical pipeline problem of getting human demonstration data onto a physical humanoid with dexterous hands without destabilizing whole-body balance — a persistent engineering challenge in this subfield.

## Links

- [Paper](https://arxiv.org/abs/2609.34724)
- [GitHub](https://github.com/WU-CVGL/DexWeave)
