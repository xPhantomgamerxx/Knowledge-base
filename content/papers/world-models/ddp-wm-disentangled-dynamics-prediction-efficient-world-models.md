---
title: "DDP-WM: Disentangled Dynamics Prediction for Efficient World Models"
date: 2026-02-02
topic: WorldModels
tags: [disentangled, dynamics, efficiency, MPC, manipulation, navigation, foreground-background, CVPR-2026]
source: https://arxiv.org/abs/2602.01780
venue: "CVPR 2026"
---

## Summary

DDP-WM introduces the Disentangled Dynamics Prediction (DDP) principle: latent state evolution is decomposed into sparse primary dynamics (driven by physical interactions) and secondary context-driven background updates. This decomposition is realized through dynamic localization to isolate foreground primary dynamics, a cross-attention mechanism for background updates, and a Low-Rank Correction Module (LRM) for background. The result is a world model that is ~9× faster at inference than dense Transformer baselines while achieving higher task success.

## Key Contributions

- Disentangled Dynamics Prediction principle separating foreground physical interactions from background context
- Four-stage decoupled process: dynamic localization → primary predictor → LRM background update
- ~9× inference speedup on Push-T task vs. state-of-the-art dense models
- Success rate improvement from 90% to 98% on Push-T with MPC planning
- Validated across navigation, tabletop manipulation, deformable-object, and multi-body interaction tasks

## Significance

Addresses the computational bottleneck of dense Transformer world models while improving performance, making real-time world-model-based planning practical for a wider range of robotic systems.

## Links

- [Paper](https://arxiv.org/abs/2602.01780)
- [GitHub](https://github.com/HCPLab-SYSU/DDP-WM)
