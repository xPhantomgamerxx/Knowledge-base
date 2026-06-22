---
title: "World Action Verifier: Self-Improving World Models via Forward-Inverse Asymmetry"
date: 2026-04-02
topic: WorldModels
tags: [self-improving, verification, forward-inverse, ICLR, action-free-data, state-plausibility]
source: https://arxiv.org/abs/2604.01985
venue: "ICLR 2026 (Outstanding Paper at World Models Workshop)"
---

## Summary

World Action Verifier (WAV) is a framework that enables world models to detect their own prediction errors and self-improve by decomposing action-conditioned state prediction into two easier sub-problems: state plausibility verification and action reachability verification. The key insight is that two asymmetries — the broader availability of action-free data and the lower dimensionality of action-relevant features — make each verification problem substantially easier than direct future prediction.

## Key Contributions

- Decomposes action-conditioned prediction into state plausibility and action reachability, each verifiable with fewer resources
- Leverages forward-inverse asymmetry: action-free data is orders of magnitude more available than action-labeled data
- Self-improvement loop: WAV identifies world-model errors without ground truth labels and uses them to guide targeted data collection or training
- Validated on multiple robotic manipulation benchmarks; recognized as Outstanding Paper at ICLR 2026 World Models Workshop

## Significance

WAV introduces a principled self-supervision signal for world model improvement — a key step toward continual, autonomous refinement of robot simulators without expensive human labeling, from a strong multi-institution team (Stanford, UCSD, CMU, Google DeepMind, Harvard).

## Links

- [Paper](https://arxiv.org/abs/2604.01985)
- [Project Page](https://world-action-verifier.github.io/)
