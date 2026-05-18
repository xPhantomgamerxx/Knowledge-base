---
title: "VLA-Forget: Vision-Language-Action Unlearning for Embodied Foundation Models"
date: 2026-04-05
topic: VLA
tags: [machine-unlearning, safety, OpenVLA, embodied-AI, benchmark]
source: https://arxiv.org/abs/2604.03956
venue: "arXiv 2604.03956"
---

## Summary

VLA-Forget is the first machine-unlearning framework specifically targeting Vision-Language-Action models, addressing the need to surgically remove unsafe, spurious, or privacy-sensitive behaviors from deployed robot policies. Because undesirable behavior in OpenVLA-style policies is distributed across the visual encoder, cross-modal projector, and language backbone, single-module edits are often insufficient—VLA-Forget adopts a component-aware unlearning strategy.

## Key Contributions

- First VLA-specific unlearning framework with a real-robot benchmark derived from Open X-Embodiment (OXE) and a controlled synthetic benchmark (lerobot/pusht_image)
- Component-aware analysis showing that effective unlearning must target perception, cross-modal grounding, and action-generation priors simultaneously
- Demonstrates targeted behavioral suppression while preserving general scene understanding and safe non-target interaction

## Significance

As VLA models move toward real-world deployment, the ability to correct dangerous or unwanted behaviors post-deployment—without full retraining—is critical; VLA-Forget introduces both the methodology and evaluation protocols for this underexplored capability.

## Links

- [Paper](https://arxiv.org/abs/2604.03956)
- [GitHub](https://github.com/raviranjan-ai/VLA-Forget)
