---
title: "RoboDream: Compositional World Models for Scalable Robot Data Synthesis"
date: 2026-06-01
topic: WorldModels
tags: [world-model, data-synthesis, video-diffusion, compositional, embodiment, sim-to-real, TRI]
source: https://arxiv.org/abs/2606.02577
venue: "arXiv 2606.02577"
---

## Summary

RoboDream is a generalizable embodiment-centric world model for scalable robot demonstration generation. It addresses the failure mode of prior video-diffusion approaches — superficial visual augmentation or embodiment hallucinations — by explicitly decoupling robot motion from its visual context.

## Key Contributions

- Three-part conditioning for the diffusion process: (1) rendered robot-only trajectory anchoring the embodiment, (2) object prior specifying target object appearance, (3) scene prior defining background environment
- Achieves photorealistic synthesis of demonstrations with novel objects, scenes, and viewpoints while preserving physically feasible robot motion
- Generated data consistently improves downstream policy performance and significantly reduces real-world data requirements across diverse manipulation tasks
- Collaboration between USC Physical Superintelligence Lab and Toyota Research Institute

## Significance

Separating embodiment motion from scene context elegantly solves hallucination while enabling open-ended compositional data augmentation, addressing a key bottleneck in scaling robot learning beyond curated lab setups.

## Links

- [Paper](https://arxiv.org/abs/2606.02577)
- [HTML](https://arxiv.org/html/2606.02577v1)
