---
title: "MARCH: Model-Assisted Reinforcement Learning for the Perceptive Control of Humanoids over Sparse Footholds"
date: 2026-06-09
topic: RL-Robotics
tags: [rl, humanoid, locomotion, model-based, teacher-student, clf-reward, sparse-footholds, tufts]
source: https://arxiv.org/abs/2606.10288
venue: "arXiv 2026"
---

## Summary

MARCH bridges model-based and model-free RL for safety-critical humanoid locomotion on sparse footholds (beams, stepping stones) where small errors cause catastrophic failure. The three-stage pipeline generates a safe reference trajectory via simplified dynamics models, trains a privileged teacher policy guided by a Control Lyapunov Function (CLF) reward built around this reference, and then distills the teacher into a vision-based student policy. Evaluated on a Unitree G1 humanoid robot, the approach produces stable, precise footstep placement across challenging terrains where pure model-free RL fails to converge.

## Key Contributions

- Combines model-based safety guarantees (CLF reward around simplified-model reference) with model-free robustness
- Privileged teacher policy using ground-truth state for structured learning before vision-based distillation
- CLF reward provides dense, safety-consistent feedback without manual reward engineering
- Successfully deployed on Unitree G1 for sparse-foothold locomotion tasks

## Significance

MARCH shows that safety-critical locomotion on sparse terrain — a major barrier to humanoid deployment — becomes tractable when simplified-model references are used to structure the RL reward, bypassing the need for careful manual reward shaping.

## Links

- [Paper](https://arxiv.org/abs/2606.10288)
