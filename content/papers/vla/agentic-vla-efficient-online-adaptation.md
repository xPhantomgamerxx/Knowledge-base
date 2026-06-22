---
title: "Agentic-VLA: Efficient Online Adaptation for Vision-Language-Action Models"
date: 2026-05-21
topic: VLA
tags: [online-adaptation, curriculum-learning, reward-synthesis, test-time-RL, agentic]
source: https://arxiv.org/abs/2605.22896
venue: "arXiv 2026"
---

## Summary

Agentic-VLA is an agentic training framework that enables VLA models to efficiently adapt online to novel environments and tasks. It addresses two critical limitations of standard VLA training: poor generalization and low sample efficiency, by dynamically synthesizing rewards, guiding exploration with a critic, and maintaining an experience memory for warm-start adaptation.

## Key Contributions

- **Adaptive Reward Synthesis**: dynamically generates and adjusts reward functions based on current VLA capabilities, decomposing complex tasks into learnable sub-goals for curriculum learning
- **Language-Guided Exploration**: a critic model provides structured, semantically grounded exploration guidance rather than random sampling
- **Experience Memory**: stores and retrieves task-relevant policy weights to warm-start adaptation on similar tasks, improving sample efficiency

## Significance

Agentic-VLA bridges the gap between offline pre-training and online deployment, providing a principled agentic loop for continuous VLA improvement without requiring large additional demonstration datasets.

## Links

- [Paper](https://arxiv.org/abs/2605.22896)
