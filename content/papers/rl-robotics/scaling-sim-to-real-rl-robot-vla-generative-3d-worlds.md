---
title: "Scaling Sim-to-Real Reinforcement Learning for Robot VLAs with Generative 3D Worlds"
date: 2026-03-19
topic: RL-Robotics
tags: [sim-to-real, RL-fine-tuning, VLA, 3D-generation, scene-diversity]
source: https://arxiv.org/abs/2603.18532
venue: "arXiv 2603.18532"
---

## Summary

This work shows that VLA models can be RL fine-tuned in simulation for generalization—without sacrificing real-world transferability—by leveraging generative 3D world models to synthesize diverse training scenes at scale. Rather than handcrafting simulation environments or fine-tuning directly in the real world, the approach automatically generates varied 3D scenes, trains with RL in those scenes, and transfers successfully to physical hardware.

## Key Contributions

- RL fine-tuning pipeline using generative 3D worlds to scale scene and object diversity without manual environment design
- Simulation success improves from 9.7% → 79.8% with 1.25× task completion speedup
- Real-world transfer improves from 21.7% → 75% success with 1.13× speedup, demonstrating effective sim-to-real transfer

## Significance

Addresses the core bottleneck of VLA sim-to-real RL fine-tuning—diversity of simulated scenes—by automating environment generation, making it practical to scale RL-based VLA improvement without the prohibitive cost of real-world data collection or manual scene design.

## Links

- [Paper](https://arxiv.org/abs/2603.18532)
