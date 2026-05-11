---
title: "Do World Action Models Generalize Better than VLAs? A Robustness Study"
date: 2026-03-23
topic: WorldModels
tags: [robustness, benchmark, generalization, VLA-comparison, LIBERO, RoboTwin, perturbation]
source: https://arxiv.org/abs/2603.22078
venue: "arXiv 2603.22078"
---

## Summary

This paper systematically compares Vision-Language-Action (VLA) models against World Action Models (WAMs) under visual and language perturbations on LIBERO-Plus and RoboTwin 2.0-Plus benchmarks. WAMs, which leverage video-data-pretrained world models for future-state prediction prior to action, consistently achieve stronger robustness: LingBot-VA reaches 74.2% on RoboTwin 2.0-Plus and Cosmos-Policy achieves 82.2% on LIBERO-Plus.

## Key Contributions

- LIBERO-Plus and RoboTwin 2.0-Plus: augmented benchmarks with systematic visual (lighting, backgrounds, object appearance) and language perturbations for robustness evaluation
- Head-to-head comparison of VLA models vs. WAMs across perturbation conditions at scale
- Identification of specific failure modes of VLAs under distribution shift that WAMs mitigate via world-model pretraining

## Significance

Provides the first large-scale empirical evidence that world model pretraining improves generalization robustness for robot policies, lending support for WAM-style architectures over pure VLAs in deployment settings.

## Links

- [Paper](https://arxiv.org/abs/2603.22078)
- [HTML](https://arxiv.org/html/2603.22078)
