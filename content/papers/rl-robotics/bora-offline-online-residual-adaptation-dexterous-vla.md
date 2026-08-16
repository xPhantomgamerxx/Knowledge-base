---
title: "BORA: Bridging Offline Reinforcement Learning and Online Residual Adaptation for Real-World Dexterous VLA Models"
date: 2026-05-28
topic: RL-Robotics
tags: [rl-robotics, vla-post-training, dexterous-manipulation, human-in-the-loop, offline-online-rl, vla-posttraining]
source: https://arxiv.org/abs/2605.30226
venue: "arXiv"
---

## Summary

BORA is a two-phase offline-to-online RL post-training framework for dexterous VLA policies. Offline, it trains a critic conditioned on both VLM cognition tokens and action chunks to give action-aware value guidance for evaluating dexterous hand motions beyond raw visual context. Online, it freezes the VLA base model and adds a lightweight, human-in-the-loop, chunk-wise residual-adaptation module that corrects offline-learned intents against real execution errors — targeting the compounding-error and sample-inefficiency problems that plague high-DoF dexterous VLA control in the real world.

## Key Contributions

- An action-conditioned critic that scores dexterous hand motions using both cognition tokens and action-chunk inputs.
- A frozen-backbone residual RL adaptation loop with human-in-the-loop correction.
- A unified offline-to-online recipe specifically targeted at dexterous (high-DoF hand) manipulation rather than parallel-gripper control.

## Strengths

- Addresses a genuinely hard regime — dexterous hands — where most VLA-RL work sticks to parallel grippers.
- The residual/frozen-base design limits real-world risk and catastrophic forgetting during online adaptation.
- Combines offline value learning with online human-in-the-loop correction rather than relying on either alone.

## Weaknesses

- Source code is withheld pending a patent filing, limiting reproducibility.
- Real-world evaluation scope appears narrow (a small number of dexterous tasks).
- Reliance on human interventions during the online phase adds operational cost.

## Open Questions

- How does BORA scale to bimanual or whole-body dexterous tasks versus the single-hand tasks reported?
- How large a human-intervention budget is required per task?
- Does the residual adaptation generalize across different VLA backbones, or only the one tested?

## Significance

A high-priority VLA post-training method that combines offline value learning with online human-in-the-loop residual correction specifically for the underexplored dexterous-hand regime.

## Links

- [Paper](https://arxiv.org/abs/2605.30226)
