---
title: "DexTouch-WM: Learning Action-Conditioned Tactile World Models from Human Touch for Dexterous Robot Manipulation"
date: 2026-09-19
topic: WorldModels
tags: [tactile, human-data, dexterous-manipulation, scaling-law, vla-posttraining]
source: https://arxiv.org/abs/2609.20649
venue: "arXiv"
---

## Summary

Learns an action-conditioned world model that jointly predicts future RGB and bilateral tactile signals, using matched piezoresistive tactile-array layouts on human and robot hands so cheap human-touch data can directly supervise robot-domain contact-dynamics prediction.

## Key Contributions

- Shared-layout piezoresistive tactile sensing across human and dexterous-robot hands plus human-motion retargeting into robot action space, making human touch data usable to supervise a robot dynamics model
- A dual-expert architecture coupling a pretrained video expert with a lightweight tactile expert via anatomy-aware tactile tokens and aligned action conditioning
- A controlled human-to-robot data scaling study (0 to 100 hours of human interaction, fixed robot supervision) showing substantial gains in held-out robot-domain visual, geometric, and contact prediction
- The learned world model is used both as an evaluation surrogate and as a generator of synthetic robot trajectories for policy learning

## Strengths

- Directly tackles the tactile-data bottleneck (robot tactile data is expensive to collect) with a scalable human-data pathway, extending the "internet human video" scaling story into touch
- Controlled ablation isolating human-data quantity while holding robot supervision fixed is a rigorous way to demonstrate real transfer rather than confounded gains
- Dual vision+tactile output makes the model usable for both planning/evaluation and contact-aware control

## Weaknesses

- Requires custom matched hardware (identical sensor layout on human glove and robot hand), limiting immediate reproducibility
- Human-to-robot transfer assumes retargeting preserves force/contact semantics; skin/glove compliance differences aren't fully characterized as a source of bias
- No reported comparison against a robot-only tactile world model at equal robot-hours, so the marginal value of human data vs. more robot teleop isn't fully isolated

## Open Questions

- Does the tactile-transfer benefit generalize across different robot hand morphologies and sensor layouts?
- How does improved contact-dynamics fidelity translate into downstream policy success rate versus just lower prediction error?

## Significance

Extends the "world models absorb cheap human data" trend from vision into touch, addressing one of dexterous manipulation's hardest data bottlenecks.

## Links

- [Paper](https://arxiv.org/abs/2609.20649)
