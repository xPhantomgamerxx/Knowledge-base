---
title: "LaST-R1: Reinforcing Robotic Manipulation via Adaptive Physical Latent Reasoning"
date: 2026-04-28
topic: RL-Robotics
tags: [RL-Robotics, VLA, latent-reasoning, chain-of-thought, GRPO, post-training, latent-CoT]
source: https://arxiv.org/abs/2604.28192
venue: "arXiv 2604.28192"
---

## Summary

LaST-R1 is an RL post-training framework for reasoning-before-acting VLA policies, introducing Latent-to-Action Policy Optimization (LAPO). LAPO jointly optimizes the latent reasoning process and action generation by embedding latent Chain-of-Thought within the RL loop. An adaptive latent CoT mechanism dynamically modulates the reasoning horizon based on environment state complexity, achieving near-perfect 99.9% average success on the LIBERO benchmark.

## Key Contributions

- Latent-to-Action Policy Optimization (LAPO): jointly optimizes latent CoT reasoning and action generation
- Adaptive latent CoT: dynamically adjusts reasoning depth based on environment state
- RL training loop integrates reasoning quality signals alongside task reward
- 99.9% average success rate on LIBERO benchmark
- Collaboration between CUHK, PKU, and Simplexity Robotics

## Significance

LaST-R1 demonstrates that RL over latent reasoning representations (not just actions) enables near-perfect manipulation performance, suggesting that chain-of-thought reasoning is as valuable in robot control as in language tasks.

## Links

- [Paper](https://arxiv.org/abs/2604.28192)
