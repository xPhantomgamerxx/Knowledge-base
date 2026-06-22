---
title: "Finetuning Vision-Language-Action Models Requires Fewer Layers Than You Think"
date: 2026-06-18
topic: VLA
tags: [efficiency, model-compression, layer-pruning, fine-tuning, training-free]
source: https://arxiv.org/abs/2606.20246
venue: "arXiv 2026"
---

## Summary

This paper reveals that large VLA models (e.g., π₀ and GR00T-N1.5) exhibit severe layer-wise representational redundancy despite being trained on diverse physical trajectories. The authors introduce a training-free structural compression pipeline using Centered Kernel Alignment (CKA) to identify and permanently remove redundant twin layers, cutting model depth by up to 50%.

## Key Contributions

- Identifies widespread layer-wise redundancy in state-of-the-art VLA models via CKA analysis
- Proposes a training-free structural compression pipeline requiring only a single forward pass
- Achieves 40–50% reduction in training time and up to 30% faster real-time inference
- Matches or exceeds base model performance after compression, validated on downstream manipulation tasks

## Significance

Demonstrates that current VLA architectures are over-parameterized for fine-tuning, offering a compute-efficient pathway to deploy billion-parameter robot policies on resource-constrained hardware.

## Links

- [Paper](https://arxiv.org/abs/2606.20246)
- [Project Page](https://clpvla.github.io/)
