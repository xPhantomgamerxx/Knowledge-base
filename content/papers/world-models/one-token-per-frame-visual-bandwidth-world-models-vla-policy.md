---
title: "One Token Per Frame: Reconsidering Visual Bandwidth in World Models for VLA Policy"
date: 2026-05-08
topic: WorldModels
tags: [visual-tokenization, flow-matching, adaptive-attention-pooling, efficiency, VLA]
source: https://arxiv.org/abs/2605.07931
venue: "arXiv 2605.07931"
---

## Summary

OneWM-VLA challenges the assumption that world-model-augmented VLAs need high visual bandwidth per frame, showing that compressing each camera view to a single semantic token via Adaptive Attention Pooling is sufficient for strong long-horizon performance. The resulting latent stream and the action trajectory are co-produced under a unified flow-matching objective, eliminating the need for a separate world-model decoder.

## Key Contributions

- Adaptive Attention Pooling that compresses each frame view to a single semantic token without compromising long-horizon performance
- Unified flow-matching objective producing latent world-model rollouts and action trajectories jointly
- Empirically demonstrates that per-frame visual bandwidth can be reduced to 1 token in world-model-augmented VLA policy learning

## Significance

By drastically reducing the visual bandwidth consumed by the world-model component of a VLA, OneWM-VLA opens the door to more computationally efficient long-horizon robot planning without sacrificing task performance.

## Links

- [Paper](https://arxiv.org/abs/2605.07931)
