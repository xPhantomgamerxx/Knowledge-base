---
title: "ThinkingVLA: Interleaved Vision and Language Reasoning for Robotic Manipulation"
date: 2026-06-16
topic: VLA
tags: [chain-of-thought, long-horizon, visual-prediction, mixture-of-transformers, subgoal-reasoning]
source: https://arxiv.org/abs/2606.17937
venue: "arXiv 2026"
---

## Summary

ThinkingVLA is a VLA model that decomposes manipulation planning into forward and inverse chain-of-thought reasoning within a unified Mixture-of-Transformers architecture. A forward CoT identifies the immediate subgoal and guides visual forecasting of the predicted next state; an inverse CoT then reasons about spatial relationships and action intent conditioned on that predicted image before generating the final action.

## Key Contributions

- Unified Mixture-of-Transformers (MoT) architecture jointly handling visual prediction and action generation
- Forward CoT identifies subgoals and predicts the target visual state as an intermediate representation
- Inverse CoT grounds action generation in the visually predicted future state, enabling richer spatial reasoning
- Consistent outperformance over state-of-the-art baselines, especially on long-horizon manipulation tasks

## Significance

Addresses the key limitation that standard VLAs map observations directly to actions without intermediate reasoning, making them brittle on long-horizon tasks; ThinkingVLA's interleaved vision-language reasoning is a strong step toward interpretable, compositional robot policies.

## Links

- [Paper](https://arxiv.org/abs/2606.17937)
