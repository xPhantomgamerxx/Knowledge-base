---
title: "OSCAR: Omni-Embodiment Action-Conditioned World Model for Robotics"
date: 2026-06-04
topic: WorldModels
tags: [world-model, video-generation, cross-embodiment, policy-evaluation, data-synthesis, cosmos]
source: https://arxiv.org/abs/2606.04463
venue: "arXiv 2606.04463"
---

## Summary

OSCAR is a precise action-conditioned video world model that generalizes across robot embodiments and enables virtual policy evaluation. It addresses three core barriers to adoption: limited scenario diversity in existing robot datasets, imprecise action following in existing video generators, and poor cross-embodiment generalization.

## Key Contributions

- Large-scale standardized data pipeline that curates, filters, and deduplicates robot and egocentric human datasets into a clean joint-training corpus spanning diverse tasks, scenarios, and embodiments
- 2D kinematic skeleton rendering as a unified conditioning representation, allowing the same conditioning approach to work for robot arms and human hands alike
- Fine-tuned from Cosmos-Predict2.5-2B; virtual policy rollouts show strong correlation with real-world evaluation outcomes
- Dataset available at Hugging Face (zywu2115/OSCAR_human)

## Significance

Demonstrates that virtual evaluation in a learned world model can reliably substitute for physical evaluation across embodiments, paving the way for purely simulated robot policy benchmarking and iteration loops.

## Links

- [Paper](https://arxiv.org/abs/2606.04463)
- [HTML](https://arxiv.org/html/2606.04463v2)
- [Dataset](https://huggingface.co/datasets/zywu2115/OSCAR_human)
