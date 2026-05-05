---
title: "Simulation Distillation: Pretraining World Models in Simulation for Rapid Real-World Adaptation"
date: 2026-03-16
topic: WorldModels
tags: [sim-to-real, world-model, latent-dynamics, online-planning, real-world-adaptation]
source: https://arxiv.org/abs/2603.15759
venue: "arXiv"
---

## Summary

SimDist addresses the sim-to-real transfer gap for world-model-based robot control by distilling structural priors — reward functions and value models — from a physics simulator into a latent world model. At deployment, the robot adapts rapidly via online planning and supervised dynamics fine-tuning in the real world, without requiring value learning from scratch. This provides dense planning signals from raw perception with minimal real-world data.

## Key Contributions

- Distills simulator reward and value models into a latent dynamics world model
- Real-world adaptation via online planning + supervised fine-tuning of latent dynamics
- Dense planning signals from raw perception at deployment (no real-world reward learning needed)
- Targets the low-data regime typical of real-world robotics

## Significance

SimDist provides a practical framework for bootstrapping world-model-based controllers from simulation and adapting them quickly to real robots, addressing a critical gap for teams that cannot afford large real-world data collection programs.

## Links

- [arXiv](https://arxiv.org/abs/2603.15759)
- [HTML version](https://arxiv.org/html/2603.15759)
