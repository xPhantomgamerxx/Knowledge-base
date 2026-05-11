---
title: "Mask World Model: Predicting What Matters for Robust Robot Policy Learning"
date: 2026-04-21
topic: WorldModels
tags: [semantic-mask, information-bottleneck, video-diffusion, generalization, robustness, distraction]
source: https://arxiv.org/abs/2604.19683
venue: "arXiv 2604.19683"
---

## Summary

Mask World Model (MWM) replaces RGB pixel prediction with semantic mask prediction in a video diffusion architecture, imposing a geometric information bottleneck that forces the model to capture essential physical dynamics and contact relations while discarding irrelevant visual distractions such as dynamic backgrounds and illumination changes. The mask-prediction world model is integrated with a diffusion-based policy head for end-to-end control.

## Key Contributions

- Semantic mask prediction as the world model target instead of RGB pixels, enforcing a geometry-focused information bottleneck
- Integration of mask-based world model with a diffusion policy head for end-to-end robot control
- Demonstrated robustness gains over standard pixel-prediction world models under visual distractor conditions

## Significance

Offers a lightweight yet principled approach to making robot world models robust to visual noise by changing what the model is asked to predict, improving generalization without requiring larger architectures or more data.

## Links

- [Paper](https://arxiv.org/abs/2604.19683)
- [HTML](https://arxiv.org/html/2604.19683)
