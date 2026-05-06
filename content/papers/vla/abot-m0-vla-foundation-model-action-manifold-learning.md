---
title: "ABot-M0: VLA Foundation Model for Robotic Manipulation with Action Manifold Learning"
date: 2026-02-11
topic: VLA
tags: [foundation-model, cross-embodiment, action-manifold, dataset, Alibaba, multi-robot, diffusion]
source: https://arxiv.org/abs/2602.11236
venue: "arXiv"
---

## Summary

ABot-M0 (Alibaba AMAP CV Lab) addresses the "one-brain, many-forms" challenge in embodied AI by building a systematic data curation pipeline and unified training strategy over six public datasets. The resulting UniACT-dataset contains over 6 million trajectories and 9,500 hours of data spanning 20+ robot morphologies. The core technical contribution, Action Manifold Learning (AML), predicts clean actions directly instead of denoising noise, yielding a more stable and efficient policy representation.

## Key Contributions

- UniACT-dataset: 6M+ trajectories, 9,500+ hours, 20+ robot embodiments, curated from 6 public datasets
- Action Manifold Learning (AML): direct clean-action prediction replacing standard noise-prediction diffusion
- Plug-and-play 3D spatial understanding module for improved precision on complex manipulation tasks
- Joint optimization of data curation pipeline, model architecture, and training strategy

## Significance

ABot-M0 demonstrates that systematic data curation combined with AML can rival or surpass larger models with ad-hoc training, positioning Alibaba's approach as a scalable path to cross-embodiment generalist manipulation.

## Links

- [Paper](https://arxiv.org/abs/2602.11236)
- [Project Page](https://amap-cvlab.github.io/ABot-Manipulation/)
- [GitHub](https://github.com/amap-cvlab/ABot-Manipulation)
