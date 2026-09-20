---
title: "OpenHLM: An Empirical Recipe for Whole-Body Humanoid Loco-Manipulation"
date: 2026-06-20
topic: Humanoid
tags: [whole-body-control, vla, teleoperation, co-training, empirical-study]
source: https://arxiv.org/abs/2606.22174
venue: "arXiv"
---

## Summary

A systematic, one-variable-at-a-time empirical study asking what it takes to build a whole-body-native VLA that maps language and pixels directly to all of a humanoid's degrees of freedom, rather than decoupling upper-body manipulation from lower-body locomotion as most existing systems do.

## Key Contributions

- Organizes findings as a three-phase roadmap: whole-body teleoperation interface design, VLA model design choices, and heterogeneous co-training strategy
- Shows a joint-based whole-body teleoperation interface outperforms interfaces that only partially expose the humanoid's DoF
- Finds a VLA pretrained on static/wheeled dual-arm platform data transfers surprisingly well to a humanoid's full action space
- Introduces co-training with "HuMI" (a humanoid analog of the Universal Manipulation Interface) to extend policies to new objects/instructions without additional whole-body teleoperation

## Strengths

- Genuinely empirical, ablation-driven methodology (rare in a field dominated by single-architecture papers) that produces actionable, falsifiable design guidance for practitioners
- The transfer-from-dual-arm-pretraining finding is a useful, somewhat counterintuitive result that could reduce the cost of humanoid-specific data collection
- HuMI co-training directly targets the teleoperation data bottleneck that is the field's most commonly cited constraint

## Weaknesses

- "Empirical recipe" papers are inherently platform- and task-specific; it's unclear how far the specific findings (e.g., which teleop interface wins) generalize across different humanoid hardware/hand designs
- No comparison against the very latest whole-body VLA baselines from major labs is described in the abstract-level material available
- One-variable-at-a-time ablation studies can miss interaction effects between design choices that a joint search might reveal

## Open Questions

- Does the "dual-arm-to-humanoid transfer" finding hold as the humanoid's kinematic chain becomes more complex (more DoF, different balance dynamics)?
- How much HuMI data is required to see the reported generalization benefits, and does quality matter more than quantity?
- Would the same one-variable-at-a-time conclusions hold on a different base VLA architecture or object/instruction distribution?

## Significance

Provides some of the first systematic, reproducible empirical guidance (rather than a single closed-source system report) for practitioners building whole-body humanoid VLA stacks, addressing a gap between well-documented upper-body manipulation VLA research and comparatively ad hoc whole-body humanoid practice.

## Links

- [Paper](https://arxiv.org/abs/2606.22174)
