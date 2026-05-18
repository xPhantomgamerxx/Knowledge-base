---
title: "TwinRL-VLA: Digital Twin-Driven Reinforcement Learning for Real-World Robotic Manipulation"
date: 2026-02-10
topic: RL-Robotics
tags: [digital-twin, sim-to-real, online-RL, exploration, VLA, smartphone-reconstruction]
source: https://arxiv.org/abs/2602.09023
venue: "arXiv 2602.09023"
---

## Summary

TwinRL-VLA addresses the twin bottlenecks of online RL for VLA manipulation—low exploration efficiency and restricted exploration space—by constructing a high-fidelity digital twin from smartphone-captured scenes and using it to guide and accelerate exploration. The framework performs parallel online RL in the digital twin, identifies failure-prone configurations, and uses these to target human-in-the-loop real-robot rollouts.

## Key Contributions

- High-fidelity digital twin reconstructed from smartphone RGB-D captures, enabling realistic bidirectional sim-to-real transfer
- Exploration space expansion strategy during SFT warm-up improves average success by 42% over real-world-only demonstrations
- Online RL with TwinRL achieves 100% in-distribution and OOD success with ≥30% speedup over prior real-world RL methods; average 20-minute training time across four tasks

## Significance

Demonstrates that an accessible digital-twin infrastructure (smartphone capture + RL parallelization) can transform the economics of online RL for VLA models, making 100% real-world task success achievable in minutes rather than hours.

## Links

- [Paper](https://arxiv.org/abs/2602.09023)
