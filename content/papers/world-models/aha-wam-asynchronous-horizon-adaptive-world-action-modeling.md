---
title: "AHA-WAM: Asynchronous Horizon-Adaptive World-Action Modeling with Observation-Guided Context Routing"
date: 2026-06-10
topic: WorldModels
tags: [world-model, wam, dual-dit, asynchronous-execution, horizon-adaptive, real-time, robotwin]
source: https://arxiv.org/abs/2606.09811
venue: "arXiv 2026"
---

## Summary

AHA-WAM resolves the tension between long-horizon world modeling and high-frequency action execution through a dual DiT architecture: a low-frequency world DiT maintains rolling key-value memory over past observations and exposes reusable layerwise latent context, while a high-frequency action DiT executes short action chunks by querying this context via layerwise joint attention. Horizon-adaptive offset training and Observation-Guided Video-Context Routing (OVCR) let the action expert exploit long-horizon world context while remaining responsive to real-time state without rerunning the world DiT. AHA-WAM achieves 92.80% on RoboTwin and 78.3% on 4 real-world tasks at 24.17 Hz — 4.59× faster than Fast-WAM — without any robot-data pretraining.

## Key Contributions

- Dual DiT architecture decoupling world planning (low-frequency) from action execution (high-frequency)
- Observation-Guided Video-Context Routing (OVCR) for responsive real-time use of long-horizon context
- Horizon-adaptive offset training enabling asynchronous execution with correct temporal alignment
- 92.80% on RoboTwin, 24.17 Hz closed-loop, 4.59× speedup over Fast-WAM; no robot-data pretraining

## Significance

AHA-WAM is the first WAM to achieve SOTA accuracy on a challenging dual-arm manipulation benchmark while simultaneously achieving real-time control speeds, demonstrating that long-horizon reasoning and reactive execution are not mutually exclusive.

## Links

- [Paper](https://arxiv.org/abs/2606.09811)
- [Project page](https://serene-sivy.github.io/aha-wam/)
