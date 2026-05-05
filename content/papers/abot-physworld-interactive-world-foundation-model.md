---
title: "ABot-PhysWorld: Interactive World Foundation Model for Robotic Manipulation with Physics Alignment"
date: 2026-03-24
topic: WorldModels
tags: [world-model, physics-alignment, diffusion-transformer, DPO, manipulation, benchmark]
source: https://arxiv.org/abs/2603.23376
venue: "arXiv"
---

## Summary

ABot-PhysWorld is a 14B Diffusion Transformer world model trained on 3 million manipulation clips annotated with physics metadata. A DPO-based post-training framework with decoupled discriminators suppresses physically implausible behaviors (object penetration, anti-gravity motion) while preserving visual quality. A parallel context block injects spatial action signals for cross-embodiment control. The authors also introduce EZSbench, the first training-independent zero-shot embodied benchmark.

## Key Contributions

- 14B DiT world model with 3M physics-annotated robot manipulation clips
- DPO-based post-training with decoupled discriminators to enforce physical plausibility
- Parallel context block for precise spatial action injection enabling cross-embodiment control
- EZSbench: first training-independent zero-shot embodied benchmark combining real and synthetic robot-task-scene combinations

## Significance

ABot-PhysWorld surpasses Veo 3.1 and Sora v2 Pro on physical plausibility and trajectory consistency benchmarks, establishing a new state-of-the-art for physics-aligned robot world models. The DPO approach for enforcing physical laws is a novel training paradigm for embodied world models.

## Links

- [arXiv](https://arxiv.org/abs/2603.23376)
- [GitHub](https://github.com/amap-cvlab/ABot-PhysWorld)
