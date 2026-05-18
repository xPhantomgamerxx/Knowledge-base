---
title: "LaWM: Least Action World Models for Long-Horizon Physical Consistency from Visual Observations"
date: 2026-05-08
topic: WorldModels
tags: [variational-integrator, Lagrangian, latent-dynamics, long-horizon, physics-consistency]
source: https://arxiv.org/abs/2605.08279
venue: "arXiv 2605.08279"
---

## Summary

LaWM operationalizes the Principle of Least Action inside a learned visual latent space: it encodes observations into generalized coordinates, learns a discrete Lagrangian over consecutive latent states, and advances predictions by solving the corresponding discrete variational integration condition. Because the latent transition is induced by a variational principle rather than an unconstrained neural function, LaWM provides a structure-preserving inductive bias for long-horizon visual prediction.

## Key Contributions

- Latent variational integrator derived from a learned discrete Lagrangian, enforcing physical consistency without explicit physics supervision
- Improved physical invariance, background consistency, motion smoothness, and geometric prediction over video-generation and world-model baselines
- Validated on both physics-clean synthetic dynamics and embodied robot interaction benchmarks

## Significance

LaWM directly addresses energy drift and physically inconsistent futures that plague existing long-horizon latent world models, offering a theoretically grounded alternative that integrates cleanly with standard robot learning pipelines.

## Links

- [Paper](https://arxiv.org/abs/2605.08279)
