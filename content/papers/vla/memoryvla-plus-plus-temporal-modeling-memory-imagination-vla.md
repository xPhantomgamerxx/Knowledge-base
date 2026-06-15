---
title: "MemoryVLA++: Temporal Modeling via Memory and Imagination in Vision-Language-Action Models"
date: 2026-06-08
topic: VLA
tags: [temporal-modeling, memory, imagination, working-memory, episodic-memory, long-horizon, VLA]
source: https://arxiv.org/abs/2606.09827
venue: "arXiv 2606.09827"
---

## Summary

MemoryVLA++ extends VLA models with a full temporal modeling framework inspired by cognitive science: working memory to buffer short-lived context, episodic memory to preserve past interactions, and an internal world model to imagine future state evolution. The majority of VLA models are single-step reactive policies that ignore temporal dependencies; MemoryVLA++ equips them with memory and imagination modules that deliver substantial gains on tasks requiring sequential reasoning and multi-step planning.

## Key Contributions

- Working memory module: buffers recent observation-action context within a sliding attention window
- Episodic memory bank: compresses and retrieves relevant past episodes for long-horizon dependency resolution
- Imagination module: internally predicts near-future visual states to guide prospective action generation
- Real-robot gains of +9% on general tasks, +26% on memory-dependent tasks, and +28% on imagination-dependent tasks over VLA baselines

## Significance

Demonstrates that cognitive-science-inspired temporal memory design yields large performance improvements on non-Markovian robot tasks, motivating memory-augmented architectures as a critical axis for next-generation VLA development.

## Links

- [Paper](https://arxiv.org/abs/2606.09827)
- [Project Page](https://shihao1895.github.io/MemoryVLA-PP-Web)
