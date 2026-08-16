---
title: "Efficient Sim-to-Real Transfer of World-Action Models from Synthetic Priors"
date: 2026-06-30
topic: WorldModels
tags: [world-models, sim-to-real, synthetic-data, cosmos-policy, zero-shot, vla-posttraining]
source: https://arxiv.org/abs/2606.31101
venue: "arXiv"
---

## Summary

Tests whether a world-action model can be trained purely from synthetic/simulated priors and deployed zero-shot in the real world. Builds on NVIDIA's Cosmos Policy (a video-diffusion model adapted for visuomotor control) and generates roughly 800 synthetic demonstrations per task via the "AnyTask" motion-planning pipeline with extensive domain randomization, with no real robot demonstrations used at all.

## Key Contributions

- First demonstrated zero-shot sim-to-real transfer specifically for a world-action model (not just a VLA policy).
- A synthetic-only training recipe built on Cosmos Policy plus AnyTask plus domain randomization.
- Quantified real-robot success rates across three task families (object lifting, drawer opening, pick-and-place with a Franka arm).

## Strengths

- Directly relevant to reducing real-world data-collection cost for WAM-style policies.
- Builds on and validates a major industry model (Cosmos Policy).
- Concrete zero-shot real-robot success numbers (35% average).

## Weaknesses

- A 35% success rate is modest, showing a real sim-to-real gap remains.
- Only three, fairly simple, task families were tested.
- Reliance on Cosmos Policy as a foundation limits independent reproducibility.

## Open Questions

- How does success rate scale with more synthetic demonstrations or greater task diversity?
- Would light real-world fine-tuning close most of the remaining gap cheaply?

## Significance

Directly matches the cross-cutting priority on synthetic data and sim-to-real pipelines for VLA-adjacent training: it is exactly the pattern of using a world model as a synthetic-data engine and then deploying zero-shot to real hardware.

## Links

- [Paper](https://arxiv.org/abs/2606.31101)
