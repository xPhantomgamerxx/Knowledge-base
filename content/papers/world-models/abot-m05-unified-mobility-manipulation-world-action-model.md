---
title: "ABot-M0.5: Unified Mobility-and-Manipulation World Action Model"
date: 2026-07-01
topic: WorldModels
tags: [WorldModels, mobile-manipulation, world-action-model, temporal-alignment, action-structure, rollout-consistency]
source: https://arxiv.org/abs/2607.00678
venue: "arXiv 2607.00678"
---

## Summary

ABot-M0.5 is a World Action Model built specifically for mobile manipulation—combining navigation and arm control within a single learned model. It identifies and addresses three fundamental bottlenecks in prior WAMs: (1) Temporal Granularity Mismatch (coarse video chunks obscure fine contact dynamics), (2) Action Structure Mismatch (entangled base and arm control spaces cause interference), and (3) Rollout Condition Mismatch (ground-truth training vs. autoregressive inference divergence causing error accumulation).

## Key Contributions

- Identifies three structural mismatches in WAMs applied to mobile manipulation
- Fine-grained temporal representation for capturing contact-level dynamics
- Disentangled action space modeling for navigation vs. arm control
- Train-test consistency mechanisms to reduce error accumulation during autoregressive rollout
- Extends ABot series to mobile manipulation scenarios

## Significance

First WAM designed explicitly for the combined challenges of mobile manipulation, offering a principled analysis of why general WAMs underperform in this setting and targeted solutions for each identified gap.

## Links

- [Paper](https://arxiv.org/abs/2607.00678)
- [GitHub](https://github.com/amap-cvlab/ABot-Manipulation)
