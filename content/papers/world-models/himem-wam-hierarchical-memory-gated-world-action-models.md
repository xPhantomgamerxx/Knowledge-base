---
title: "HiMem-WAM: Hierarchical Memory-Gated World Action Models for Robotic Manipulation"
date: 2026-06-10
topic: WorldModels
tags: [WorldModels, hierarchical-memory, skill-learning, long-horizon, latent-actions, memory-gating]
source: https://arxiv.org/abs/2606.10363
venue: "arXiv 2606.10363"
---

## Summary

HiMem-WAM is a Hierarchical Memory-Gated World Action Model that integrates motion-centric latent actions, high-level skill latents, and boundary-triggered memory updates. A joint hierarchical latent framework learns low-level motion and high-level skill representations simultaneously, while a boundary-aware memory gate writes compact task states at predicted skill transitions—enabling causal inference without test-time video generation or optical flow estimation.

## Key Contributions

- Hierarchical latent framework jointly learning low-level motion and high-level skill latents
- Boundary-aware memory gate triggered at predicted skill transitions (not every step)
- Enables robust long-horizon manipulation without test-time video generation
- Evaluated on LIBERO, LIBERO-PLUS, RMBench, and real-world tasks
- Hierarchical latents improve robustness under deployment perturbations

## Significance

Hierarchical temporal abstraction in world action models provides better structure for long-horizon tasks; the skill-boundary-triggered memory gate is an elegant way to avoid redundant writes while maintaining causal coherence.

## Links

- [Paper](https://arxiv.org/abs/2606.10363)
