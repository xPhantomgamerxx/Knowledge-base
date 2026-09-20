---
title: "rMuscle: Robotic Muscle Memory for Efficient Vision-Language-Action Model Inference"
date: 2026-09-16
topic: VLA
tags: [inference-efficiency, caching, edge-deployment, real-time-control]
source: https://arxiv.org/abs/2609.19104
venue: "arXiv"
---

## Summary

Proposes a dual-phase "muscle-memory" cache for VLA inference that exploits cross-execution similarity in repeated robot tasks — a Context Cache reuses visual-token computations and an Action Cache reuses neuron activation patterns — to cut latency without retraining the underlying VLA.

## Key Contributions

- Empirical characterization of cross-execution similarity in embodied workloads, extending beyond observations/actions to internal model activation states
- Dual-cache design (visual-token reuse + neuron-activation reuse) with online recomputation and sliding-window retrieval to bound memory/access overhead
- Mask sharing across consecutive denoising steps for diffusion/flow-based action heads

## Strengths

- Training-free, plug-in efficiency method — broadly applicable across existing VLA backbones rather than requiring a new architecture
- Evaluated on both simulation (LIBERO, RoboTwin) and physical hardware (RTX 4090, Jetson Thor), with success-rate parity claims, not just latency numbers

## Weaknesses

- Gains (1.29–1.42x) are moderate rather than transformative, and the paper doesn't report worst-case behavior when the cross-execution similarity assumption breaks (e.g., genuinely novel scenes)
- Cache staleness/invalidation policy is only lightly described; edge cases in dynamic environments are unclear

## Open Questions

- How does performance degrade for long-horizon tasks with substantial environment variation between executions?
- Does the cache mechanism interact poorly with online RL fine-tuning or test-time adaptation methods that intentionally shift activations?

## Significance

Practical inference-latency work is a necessary complement to model-capability papers, since VLA responsiveness directly bounds real-world deployability on edge hardware.

## Links

- [Paper](https://arxiv.org/abs/2609.19104)
