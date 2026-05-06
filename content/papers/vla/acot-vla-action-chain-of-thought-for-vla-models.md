---
title: "ACoT-VLA: Action Chain-of-Thought for Vision-Language-Action Models"
date: 2026-01-16
topic: VLA
tags: [chain-of-thought, action-reasoning, CVPR-2026, manipulation, explicit-reasoning, diffusion]
source: https://arxiv.org/abs/2601.11404
venue: "CVPR 2026"
---

## Summary

ACoT-VLA introduces Action Chain-of-Thought (ACoT), a paradigm that formulates the reasoning process as a structured sequence of coarse action intents that directly guide the final policy in action space. Unlike prior work that reasons via sub-task text or goal images, ACoT reasons in the native action modality, making intermediate guidance more directly actionable. The architecture pairs an Explicit Action Reasoner (EAR) with an Implicit Action Reasoner (IAR) to produce both coarse trajectory proposals and latent action priors.

## Key Contributions

- Action Chain-of-Thought (ACoT): reasoning formulated as coarse action-intent sequences, not text or goal images
- Explicit Action Reasoner (EAR): generates coarse reference trajectories as explicit intermediate reasoning steps
- Implicit Action Reasoner (IAR): extracts latent action priors from internal multimodal representations
- Accepted at CVPR 2026 with open-source implementation from AgibotTech

## Significance

By placing the reasoning chain directly in action space, ACoT-VLA closes the modality gap between high-level planning and low-level execution, enabling more precise manipulation than text- or image-based intermediate reasoning approaches.

## Links

- [Paper](https://arxiv.org/abs/2601.11404)
- [GitHub](https://github.com/AgibotTech/ACoT-VLA)
