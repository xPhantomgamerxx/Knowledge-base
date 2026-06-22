---
title: "Accelerating and Scaling MPC-Guided Reinforcement Learning for Humanoid Locomotion and Manipulation"
date: 2026-06-04
topic: RL-Robotics
tags: [MPC, humanoid, locomotion, manipulation, parallel-MPC, centroidal-dynamics, GPU-accelerated]
source: https://arxiv.org/abs/2606.05687
venue: "arXiv 2026"
---

## Summary

This paper studies efficient integration of Model Predictive Control (MPC) as a training-time reward signal for humanoid RL, combining the physical grounding of MPC with the robustness and whole-body skill diversity of large-scale RL. The key contribution is π^nMPC, a parallel-in-horizon, construction-free GPU MPC solver that operates directly on time-varying centroidal dynamics, making MPC guidance practical inside massively parallel RL training.

## Key Contributions

- Centroidal-dynamics MPC reward formulation that provides physically grounded guidance during RL training
- π^nMPC: a GPU-native parallel MPC solver that avoids expensive problem pre-compilation and reduces training overhead
- Scales to massively parallel RL environments without prohibitive memory or compute costs
- Validated on humanoid locomotion and manipulation tasks at Caltech and Johns Hopkins

## Significance

Brings MPC's constraint satisfaction and physical grounding directly into large-scale RL for humanoids, addressing a longstanding bottleneck where MPC-guided RL was too slow to be practical for real-scale training.

## Links

- [Paper](https://arxiv.org/abs/2606.05687)
