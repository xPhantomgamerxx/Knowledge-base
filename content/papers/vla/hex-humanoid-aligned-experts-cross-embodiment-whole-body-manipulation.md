---
title: "HEX: Humanoid-Aligned Experts for Cross-Embodiment Whole-Body Manipulation"
date: 2026-04-09
topic: VLA
tags: [humanoid, whole-body, mixture-of-experts, cross-embodiment, loco-manipulation, history-tokens]
source: https://arxiv.org/abs/2604.07993
venue: "arXiv 2026"
---

## Summary

HEX is a state-centric VLA framework for coordinated whole-body manipulation on full-sized bipedal humanoid robots. It introduces a humanoid-aligned universal state representation for scalable learning across heterogeneous embodiments, and a Mixture-of-Experts Unified Proprioceptive Predictor to model whole-body coordination and temporal motion dynamics from large-scale multi-embodiment trajectory data. Lightweight history tokens summarize past observations for efficient temporal context without repeated image re-encoding.

## Key Contributions

- Humanoid-aligned universal state representation enabling cross-embodiment scalability
- Mixture-of-Experts Unified Proprioceptive Predictor for whole-body coordination modeling
- Lightweight history-token mechanism for efficient temporal context during inference
- State-of-the-art performance on real-world humanoid manipulation tasks, especially in fast-reaction and long-horizon scenarios

## Significance

Addresses a critical gap in VLA research by enabling coordinated whole-body humanoid control where most existing approaches treat robot body parts independently, filling a key requirement for practical humanoid deployment.

## Links

- [Paper](https://arxiv.org/abs/2604.07993)
- [Project Page](https://hex-humanoid.github.io/)
- [GitHub](https://github.com/Open-X-Humanoid/HEX)
