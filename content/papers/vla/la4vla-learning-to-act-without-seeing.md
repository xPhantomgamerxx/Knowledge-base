---
title: "LA4VLA: Learning to Act without Seeing via Language-Action Pretraining"
date: 2026-06-25
topic: VLA
tags: [vla, language-action-pretraining, language-grounding, data-efficient, pretraining]
source: https://arxiv.org/abs/2606.27295
venue: "arXiv 2026"
---

## Summary

LA4VLA addresses a training imbalance in standard VLAs: dense visual-action supervision dominates the comparatively sparse language-action signal, causing policies to rely on visual shortcuts and fail when language conditions novel action combinations. The framework decomposes expert demonstration trajectories into atomic action segments and pairs each with a low-level language description, yielding the LA4-33K dataset (33K language-action episodes from existing demonstrations, no extra robot data). A 1B-parameter LA4VLA-1B policy pretrained on LA4-33K and then fine-tuned with standard VLA objectives consistently outperforms matched baselines, gaining up to +17.8 pp in simulation and +45.0 pp on real-world tasks.

## Key Contributions

- Identifies and addresses the language-action grounding imbalance in standard VLA pretraining
- LA4-33K: 33K language-action episodes derived from existing demonstrations without additional robot data collection
- Three paradigms for incorporating language-action supervision (pretrain, mixed, sequential)
- LA4VLA-1B: +17.8 pp simulation / +45.0 pp real-world over matched VLA-pretrained baselines

## Significance

LA4VLA shows that the language-conditioning signal in robotics data is routinely overwhelmed by visual features, and that a simple restructuring of pretraining data can unlock large real-world gains without additional robot collection.

## Links

- [Paper](https://arxiv.org/abs/2606.27295)
