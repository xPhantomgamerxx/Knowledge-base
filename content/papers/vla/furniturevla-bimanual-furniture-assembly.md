---
title: "FurnitureVLA: Learning Long-Horizon Bimanual Furniture Assembly with Vision-Language-Action Model"
date: 2026-07-01
topic: VLA
tags: [vla, bimanual-manipulation, synthetic-data, vla-posttraining]
source: https://arxiv.org/abs/2607.01212
venue: "arXiv"
---

## Summary

FurnitureVLA presents what the authors describe as the first systematic study of real-scale bimanual furniture assembly using vision-language-action models, tackling long-horizon tasks (up to 7 subtasks, 1550 control steps) via a scalable simulation data-generation pipeline, a VR teleoperation system for single-operator bimanual real-world data collection, and a "progress-enhanced" VLA that jointly predicts actions and a continuous task-progress signal. It matters because furniture assembly is a genuinely hard, long-horizon, contact-rich bimanual benchmark that stresses compounding-error problems far beyond typical short-horizon pick-and-place VLA evaluations.

## Key Contributions

- A scalable simulation pipeline for generating expert demonstrations and evaluation scenarios for bimanual furniture assembly tasks
- A VR teleoperation system enabling a single human operator to control both arms simultaneously for collecting high-quality real-world bimanual demonstrations
- A progress-enhanced VLA architecture that is fine-tuned on semantically grounded subtasks and jointly predicts the action and a continuous progress estimate, enabling automatic subtask transitions during inference and reducing compounding errors across long horizons
- Empirical results: average simulation success improves from 48% to 80% versus baselines across three furniture types
- Real-world validation on a Kinova Gen3 platform, with only a 16% success drop on the hardest task relative to simulation

## Strengths

- Furniture assembly is a well-chosen stress test for long-horizon bimanual VLA: it requires precise sequencing, bimanual coordination, and recovery from small errors compounding over up to 1550 control steps — a much harder regime than typical short-horizon manipulation benchmarks
- The progress-signal co-prediction is a sensible, relatively lightweight architectural addition to combat compounding error and automate subtask transitioning without needing hand-crafted state machines
- Includes both simulation-scale evaluation (for statistical breadth) and real-hardware validation (Kinova Gen3), giving more confidence than a sim-only study
- The reported real-world gap (only 16% drop on the hardest task) is a relatively strong sim-to-real transfer result for such a long-horizon, contact-rich task class

## Weaknesses

- Even with the proposed method, baseline success at 48% (before the progress-enhancement fix) suggests the underlying task is still quite difficult, and the 80% achieved figure, while a large relative improvement, still implies a meaningful residual failure rate for real deployment purposes
- Evaluated on only three furniture types — generalization to the vast diversity of real furniture assembly tasks (different joint mechanisms, parts counts, tolerances) is not established
- Reliance on VR teleoperation for real-world data collection is inherently costly and operator-skill-dependent, limiting how easily this data collection approach scales compared to fully autonomous or crowdsourced approaches (cf. AXIS)
- The continuous progress signal requires subtask-level semantic grounding/labeling during training data preparation, adding annotation overhead not present in end-to-end action-only VLA training

## Open Questions

- How does the progress-enhanced VLA's subtask-transition mechanism handle truly novel failure recoveries (e.g., a dropped part) that fall outside the expected progress trajectory?
- Would the approach generalize to furniture assembly tasks requiring tools (screwdrivers, wrenches) rather than purely manual part-fitting?
- How sensitive is the sim-to-real transfer gap to the specific choice of Kinova Gen3 versus other bimanual arm configurations, particularly ones with different reach/precision characteristics?
- Is the progress-prediction auxiliary head necessary, or would simpler subtask segmentation heuristics achieve similar gains?

## Significance

FurnitureVLA pushes VLA evaluation toward genuinely long-horizon, contact-rich, bimanual tasks rather than the short-horizon single-arm pick-and-place tasks that dominate much of the VLA literature, and its progress-conditioned architecture offers a transferable idea (joint action + progress prediction) for combating compounding errors in other long-horizon manipulation domains.

## Links

- [Paper](https://arxiv.org/abs/2607.01212)
