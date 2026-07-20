---
title: "Xiaomi-Robotics-U0: Unified Embodied Synthesis with World Foundation Model"
date: 2026-07-14
topic: WorldModels
tags: [world-model, embodied-synthesis, data-augmentation, multi-view, scene-generation, transfer, xiaomi]
source: https://arxiv.org/abs/2607.11643
venue: "arXiv 2607.11643"
---

## Summary

Xiaomi-Robotics-U0 is a 38B-parameter multimodal autoregressive world foundation model for unified embodied synthesis. It supports multi-view scene generation across multiple robot embodiments and introduces structured, controllable embodied transfer — moving robot trajectories to new environments while preserving arm pose and motion. Jointly optimized across text-to-image, image editing, embodied scene generation, and embodied video generation tasks, it achieves an 82× speedup in data generation (from 450s to 5.4s per image) via parallel decoding.

## Key Contributions

- 38B multimodal autoregressive model jointly trained across five embodied and image generation objectives
- Embodied scene generation: creates multi-view initial scenes from text descriptions across diverse environments
- Embodied transfer: moves existing trajectories to new environments with configurable lighting, background, surface, and object changes
- 82× generation speedup via parallel decoding optimization
- +26 percentage-point improvement on real-world manipulation OOD success rate (π₀.₅: 36.9% → 63.2%) using synthesized data

## Significance

Xiaomi's open-sourced world foundation model demonstrates that embodied data synthesis can dramatically boost policy generalization — the 26-point OOD improvement with synthetic augmentation is among the strongest reported results for data-engine-driven VLA improvement.

## Links

- [Paper](https://arxiv.org/abs/2607.11643)
- [Project Page](https://robotics.xiaomi.com/xiaomi-robotics-u0.html)
