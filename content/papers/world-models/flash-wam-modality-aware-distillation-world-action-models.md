---
title: "Flash-WAM: Modality-Aware Distillation for World Action Models"
date: 2026-06-03
topic: WorldModels
tags: [world-model, wam, knowledge-distillation, consistency-distillation, inference-efficiency, video-generation, northeastern]
source: https://arxiv.org/abs/2606.05254
venue: "arXiv 2026"
---

## Summary

WAMs generate future video and robot actions through iterative diffusion requiring tens of denoising steps, which precludes real-time control. Flash-WAM identifies that off-the-shelf consistency distillation fails in the joint video-action setting because video and action streams use different SNR-shifted noise schedules — a fundamental asymmetry single-modality distillation cannot handle. Flash-WAM introduces modality-aware step distillation: a linear-gradient-scaling parametrization for the action stream's low-noise regime, paired with a variance-preserving parametrization for the video stream's high-noise regime. The result is a few-step WAM that maintains task performance while dramatically reducing inference cost.

## Key Contributions

- Identifies the modality-SNR asymmetry problem preventing standard consistency distillation from working in joint video-action models
- Linear-gradient-scaling parametrization for action streams (low-noise regime)
- Variance-preserving parametrization for video streams (high-noise regime)
- Enables practical real-time WAM control with negligible task performance loss

## Significance

Flash-WAM is the first principled solution to the speed bottleneck of WAMs, enabling the joint video-action diffusion paradigm to run at interactive rates — a prerequisite for real-world deployment.

## Links

- [Paper](https://arxiv.org/abs/2606.05254)
- [Project page](https://flashwam.github.io)
