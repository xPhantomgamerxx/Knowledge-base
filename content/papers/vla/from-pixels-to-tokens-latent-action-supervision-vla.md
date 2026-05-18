---
title: "From Pixels to Tokens: A Systematic Study of Latent Action Supervision for Vision-Language-Action Models"
date: 2026-05-06
topic: VLA
tags: [latent-action, pretraining, cross-embodiment, image-based, action-based]
source: https://arxiv.org/abs/2605.04678
venue: "arXiv 2605.04678"
---

## Summary

This paper systematically compares two families of latent action supervision for VLAs—image-based (trajectory regularization via visual predictions) and action-based (unifying target spaces through discretized action tokens)—and characterizes which formulation best suits which type of task. The study finds a clear formulation-task correspondence and concludes that directly supervising the VLM backbone with discrete latent action tokens yields the strongest overall performance.

## Key Contributions

- Structured taxonomy dividing latent action supervision into image-based (scene-level, long-horizon) and action-based (motor-coordination, complex execution) families
- Empirical finding: image-based latent actions excel at long-horizon reasoning and scene generalization; action-based latent actions excel at precise motor coordination
- Discrete latent action token supervision of the VLM backbone outperforms all other formulations across benchmarks

## Significance

By demystifying the fragmented latent-action literature and establishing clear task-formulation correspondences, this work provides actionable design guidelines for future VLA pretraining pipelines that must operate across heterogeneous datasets and embodiments.

## Links

- [Paper](https://arxiv.org/abs/2605.04678)
