---
title: "Physically Native World Models: A Hamiltonian Perspective on Generative World Modeling"
date: 2026-05-01
topic: WorldModels
tags: [Hamiltonian-dynamics, phase-space, physics-grounded, latent-dynamics, model-based-RL]
source: https://arxiv.org/abs/2605.00412
venue: "arXiv 2605.00412"
---

## Summary

This position/perspective paper proposes Hamiltonian World Models as a unified physically grounded framework for world modeling, covering the three currently fragmented routes: 2D video-generative models, 3D scene-centric models, and JEPA-like latent models. The core idea is to encode observations into a structured latent phase space, evolve it through Hamiltonian-inspired dynamics with control, dissipation, and residual terms, and decode predicted trajectories into future observations for planning.

## Key Contributions

- Theoretical framework unifying video generation, 3D reconstruction, and latent prediction under Hamiltonian dynamics
- Analysis of how Hamiltonian structure may improve interpretability, data efficiency, and long-horizon stability for robotic world models
- Discussion of practical challenges (friction, contact, non-conservative forces, deformables) and proposed research directions

## Significance

Provides a theoretically rigorous bridge between classical mechanics and modern generative world models, potentially enabling more stable and interpretable long-horizon rollouts in model-based robot RL.

## Links

- [Paper](https://arxiv.org/abs/2605.00412)
