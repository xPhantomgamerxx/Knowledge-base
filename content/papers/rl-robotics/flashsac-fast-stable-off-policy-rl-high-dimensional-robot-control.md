---
title: "FlashSAC: Fast and Stable Off-Policy Reinforcement Learning for High-Dimensional Robot Control"
date: 2026-04-06
topic: RL-Robotics
tags: [off-policy, SAC, dexterous-manipulation, high-dimensional, humanoid, sim-to-real, stability]
source: https://arxiv.org/abs/2604.04539
venue: "arXiv 2604.04539"
---

## Summary

FlashSAC is a scalable off-policy RL algorithm built on Soft Actor-Critic that sharply reduces gradient update frequency while compensating with larger models and higher data throughput, enabling stable training in high-dimensional robot control settings. It explicitly bounds weight, feature, and gradient norms to prevent critic error accumulation under the broader state-action distributions sampled during off-policy learning.

## Key Contributions

- Reduced gradient update schedule compensated by larger network capacity and increased replay throughput, improving training efficiency
- Explicit norm bounding (weight, feature, gradient) to maintain critic stability under diverse off-policy data
- Evaluated on 60+ tasks across 10 simulators, consistently outperforming PPO and strong off-policy baselines
- Reduces humanoid locomotion sim-to-real training time from hours to minutes; largest gains on dexterous manipulation

## Significance

Demonstrates that off-policy methods can match or exceed on-policy stability with appropriate regularization, reopening the efficiency advantages of SAC-class algorithms for challenging high-dimensional robot control tasks.

## Links

- [Paper](https://arxiv.org/abs/2604.04539)
- [HTML](https://arxiv.org/html/2604.04539)
- [GitHub](https://github.com/Holiday-Robot/FlashSAC)
