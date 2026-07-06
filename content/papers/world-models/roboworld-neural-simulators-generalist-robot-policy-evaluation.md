---
title: "RoboWorld: Fast and Reliable Neural Simulators for Generalist Robot Policy Evaluation"
date: 2026-07-01
topic: WorldModels
tags: [WorldModels, policy-evaluation, neural-simulator, generalist-robot, video-world-model, VLM-scoring]
source: https://arxiv.org/abs/2607.01060
venue: "arXiv 2607.01060"
---

## Summary

Video world models are emerging as scalable alternatives for evaluating generalist robot policies without physical hardware. RoboWorld is an automated evaluation pipeline pairing a fast autoregressive video world model with a task-progress-aware vision-language model scorer, enabling reliable policy benchmarking at scale without robot access.

## Key Contributions

- Automated evaluation pipeline: autoregressive video world model + VLM-based task-progress scoring
- Fast inference enabling scalable policy evaluation across diverse tasks
- Task-progress-aware scoring that goes beyond binary success/failure
- Reduces evaluation cost and engineering burden of physical robot benchmarking

## Significance

RoboWorld validates world models as policy evaluation tools—a complementary use case beyond planning and data generation—potentially enabling continuous policy monitoring and large-scale benchmarking that would be prohibitive with physical robots.

## Links

- [Paper](https://arxiv.org/abs/2607.01060)
