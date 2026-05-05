---
title: "DreamDojo: A Generalist Robot World Model from Large-Scale Human Videos"
date: 2026-02-06
topic: WorldModels
tags: [world-model, human-video, dexterous-manipulation, NVIDIA, generalist, egocentric]
source: https://arxiv.org/abs/2602.06949
venue: "arXiv"
---

## Summary

NVIDIA's DreamDojo learns diverse robot manipulation skills from 44,000 hours of egocentric human video — the largest video dataset for robot world model pretraining to date. The key insight is using continuous latent actions as unified proxy actions for unlabeled video, which enables rich interaction knowledge transfer. After lightweight post-training on small-scale robot data, DreamDojo demonstrates strong physics understanding, precise action controllability, and real-time inference at 10.81 FPS via a distillation pipeline.

## Key Contributions

- 44k-hour egocentric human video pretraining dataset spanning diverse daily scenarios and objects
- Continuous latent actions as a unified proxy for learning from action-unlabeled video
- Post-training on small-scale robot data with strong transfer of physics and dexterity
- Distillation pipeline enabling real-time inference at 10.81 FPS from a large world model

## Significance

DreamDojo demonstrates that human egocentric video — abundant and cheaply sourced — can bootstrap powerful robot world models without requiring robot action labels, substantially reducing the data collection burden for generalizable manipulation policies.

## Links

- [arXiv](https://arxiv.org/abs/2602.06949)
- [GitHub](https://github.com/NVIDIA/DreamDojo)
- [Project Page](https://dreamdojo-world.github.io/)
