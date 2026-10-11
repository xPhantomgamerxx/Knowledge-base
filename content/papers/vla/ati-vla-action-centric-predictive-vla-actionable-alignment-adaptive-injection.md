---
title: "ATI-VLA: Action-Centric Predictive Vision-Language-Action Models via Actionable Alignment Then Adaptive Injection"
date: 2026-10-01
topic: VLA
tags: [vla, predictive-models, architecture, robotics]
source: https://arxiv.org/abs/2610.01741
venue: "arXiv / NeurIPS 2026"
---

## Summary

ATI-VLA tackles the common finding that predictive VLA models (ones that also forecast future states) underperform pure action-prediction models, attributing the gap to modality misalignment between observations/actions and conflicting joint-optimization objectives. It aligns observation and action representations through a shared discrete codebook, then injects the resulting predictive latents into action decoding via a lightweight side-path, reporting 97.9% average success on LIBERO (first among compared methods) and 70% on long-horizon real-robot tasks on a Galaxea R1 Lite.

## Key Contributions

- Diagnosis of why predictive VLAs often lag pure action models: modality misalignment and joint-optimization conflict.
- A two-stage "Actionable Alignment Then Adaptive Injection" recipe: shared discrete codebook alignment, followed by lightweight side-path injection of predictive latents into the action decoder.
- State-of-the-art reported LIBERO result among compared predictive-VLA methods, plus long-horizon real-robot validation.

## Strengths

- Directly addresses a known weakness in the predictive-VLA sub-field rather than just adding another prediction loss.
- The lightweight side-path design means the predictive signal can help without requiring the action decoder to be jointly optimized against a conflicting objective from scratch.
- Real-robot long-horizon evaluation, not just simulation benchmarks.

## Weaknesses

- Numbers come from the authors' own tables and are not independently verified.
- The side-path/injection mechanism adds architectural complexity, and its sensitivity to codebook size/design isn't detailed in the available material.

## Open Questions

- How much of the gain comes from the alignment stage versus the injection mechanism — is one necessary without the other?
- Does the approach generalize to other predictive targets (e.g., depth, affordance maps) beyond whatever future-state representation was used?

## Significance

A targeted fix to a recognized failure mode in predictive VLA models, relevant to the broader debate (also touched by "Where Predictive Supervision Goes...") about how best to fuse future-prediction objectives into action-generating policies.

## Links

- [Paper](https://arxiv.org/abs/2610.01741)
