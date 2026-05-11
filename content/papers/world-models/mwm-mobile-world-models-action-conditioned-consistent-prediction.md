---
title: "MWM: Mobile World Models for Action-Conditioned Consistent Prediction"
date: 2026-03-08
topic: WorldModels
tags: [navigation, action-conditioned, consistency, diffusion, planning, sim-to-real]
source: https://arxiv.org/abs/2603.07799
venue: "arXiv 2603.07799"
---

## Summary

MWM presents a world model for image-goal navigation that addresses action-conditioned consistency failures under multi-step rollout, which degrade planning quality even when individual frames are visually plausible. It uses a two-stage training pipeline: structure pretraining followed by Action-Conditioned Consistency (ACC) post-training that explicitly trains under self-conditioned rollout contexts to reduce error accumulation.

## Key Contributions

- Action-Conditioned Consistency (ACC) post-training stage to align autoregressive predictions with real observations under rollout
- Inference-Consistent State Distillation (ICSD): extends consistency distillation to few-step diffusion while preserving action-conditioned rollout consistency
- Two-stage framework enabling efficient deployment with few-step inference without sacrificing planning coherence

## Significance

Addresses a critical but underappreciated failure mode of navigation world models — rollout drift — with a principled consistency-enforcement framework applicable broadly to diffusion-based world models.

## Links

- [Paper](https://arxiv.org/abs/2603.07799)
- [HTML](https://arxiv.org/html/2603.07799v1)
- [GitHub](https://github.com/AIGeeksGroup/MWM)
