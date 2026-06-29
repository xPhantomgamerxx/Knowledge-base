---
title: "Qwen-VLA: Unifying Vision-Language-Action Modeling across Tasks, Environments, and Robot Embodiments"
date: 2026-05-29
topic: VLA
tags: [vla, unified-model, cross-embodiment, navigation, manipulation, alibaba, qwen]
source: https://arxiv.org/abs/2605.30280
venue: "arXiv 2026"
---

## Summary

Qwen-VLA extends Alibaba's Qwen vision-language stack to continuous action and trajectory generation via a DiT-based action decoder, unifying manipulation, navigation, and trajectory prediction in a single embodied foundation model. It uses embodiment-aware prompt conditioning to specify robot type and control conventions, enabling generalization across diverse robot platforms and task categories. Joint pretraining over robotics trajectories, egocentric human demos, synthetic simulation data, and navigation corpora yields consistent multi-task performance and strong OOD generalization.

## Key Contributions

- Unified VLA covering manipulation, navigation, and trajectory-centric prediction with a single policy backbone
- Embodiment-aware prompt conditioning via robot-specific textual descriptions for cross-embodiment control
- Large-scale joint pretraining over heterogeneous data (robot demos, egocentric human data, VLN, simulation)
- 97.9% on LIBERO, 73.7% on SimplerEnv-WidowX, 86.1%/87.2% on RoboTwin-Easy/Hard; 69.0% OSR on R2R navigation

## Significance

Qwen-VLA is a rare example of a single model handling both manipulation and navigation benchmarks with competitive results across all, providing strong evidence for the unified-VLA hypothesis and a powerful open baseline from the Alibaba ecosystem.

## Links

- [Paper](https://arxiv.org/abs/2605.30280)
- [Blog](https://qwen.ai/blog?id=qwenvla)
