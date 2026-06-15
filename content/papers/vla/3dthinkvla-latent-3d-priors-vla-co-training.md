---
title: "3DThinkVLA: Endowing Vision-Language-Action Models with Latent 3D Priors via 3D-Thinking-Guided Co-training"
date: 2026-06-04
topic: VLA
tags: [3D-spatial-reasoning, latent-priors, co-training, geometry, VLA, spatial-grounding]
source: https://arxiv.org/abs/2606.04436
venue: "arXiv 2606.04436"
---

## Summary

3DThinkVLA is a co-training framework that injects latent 3D spatial priors into standard VLA models without modifying their backbone architecture. It identifies a "prompt-induced reasoning gap" — standard action prompts inadvertently deactivate learned 3D spatial priors — and corrects it via a shared reasoning anchor token that preserves geometric context throughout action generation.

## Key Contributions

- Latent 3D geometry perception module: aligns intermediate VLM visual features with a 3D foundation model to inject low-level geometric cues at the feature level without backbone changes
- Online 3D reasoning distillation: uses a shared reasoning anchor token (the first output token) emitted during 3D VLM co-training to robustly propagate spatial priors into the action sequence
- Identification and formal characterisation of the prompt-induced reasoning gap in VLA co-training
- Demonstrated improved manipulation performance on tasks requiring precise spatial understanding

## Significance

Shows that 3D spatial reasoning capability can be distilled into standard 2D VLAs through a lightweight co-training regime, making high-quality geometric priors accessible without depth sensors or 3D-specific architectural redesigns.

## Links

- [Paper](https://arxiv.org/abs/2606.04436)
- [HTML](https://arxiv.org/html/2606.04436)
