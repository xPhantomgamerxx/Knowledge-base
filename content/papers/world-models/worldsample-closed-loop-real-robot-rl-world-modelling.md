---
title: "WorldSample: Closed-loop Real-robot RL with World Modelling"
date: 2026-07-02
topic: WorldModels
tags: [WorldModels, real-robot-RL, data-augmentation, synthetic-training, sim-to-real, closed-loop]
source: https://arxiv.org/abs/2607.02431
venue: "arXiv 2607.02431"
---

## Summary

WorldSample is a physically grounded data augmentation framework for real-robot RL that closes the loop between physical rollouts, world-model generation, and policy improvement. Grounded on real robot rollouts, WorldSample uses a post-trained world model to generate high-fidelity synthetic transitions, substantially reducing visual hallucination and enabling more sample-efficient real-robot learning.

## Key Contributions

- Closed-loop real-synthetic pipeline: real rollouts → world model generation → policy improvement → repeat
- Post-trained world model (grounded on real data) generates realistic synthetic transitions
- Reduces visual hallucination compared to ungrounded world model augmentation
- Enables more sample-efficient RL on physical hardware by augmenting real experience
- Evaluated on contact-rich manipulation tasks

## Significance

WorldSample bridges real-robot RL and world model simulation by grounding generation on actual hardware data, making world models practically useful for accelerating on-hardware learning—not just offline planning.

## Links

- [Paper](https://arxiv.org/abs/2607.02431)
