---
title: "GeoSem-WAM: Geometry- and Semantic-Aware World Action Models"
date: 2026-06-02
topic: WorldModels
tags: [world-action-model, geometry, semantics, latent-representation, embodied-ai, wam]
source: https://arxiv.org/abs/2606.03188
venue: "arXiv 2606.03188"
---

## Summary

GeoSem-WAM proposes a structured world modeling framework that enhances World Action Model (WAM) latent representations through explicit geometric and semantic supervision. Standard WAMs rely on RGB future prediction, which provides limited structural and spatial understanding. The paper also investigates whether WAM effectiveness comes from explicit future imagination at inference or from representation learning induced by predictive pretraining.

## Key Contributions

- Geometric supervision stream augmenting WAM latent representations with 3D structural understanding of manipulation scenes
- Semantic supervision stream injecting task-relevant semantic priors to support richer action grounding
- Analysis showing WAM's primary advantage lies in learning robust latent representations rather than generating future observations at test time — a key insight for WAM design
- Outperforms RGB-only WAM baselines on embodied manipulation benchmarks

## Significance

Provides both a practical improvement (geometry + semantics improve WAM representations) and an important theoretical clarification (representation learning, not inference-time imagination, drives WAM gains), reshaping how the field should design and evaluate world action models.

## Links

- [Paper](https://arxiv.org/abs/2606.03188)
- [HTML](https://arxiv.org/html/2606.03188v1)
