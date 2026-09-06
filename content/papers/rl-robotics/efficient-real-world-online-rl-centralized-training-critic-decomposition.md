---
title: "Efficient Real-World Online Reinforcement Learning for Robot Manipulation via Centralized Training and Critic Decomposition"
date: 2026-08-10
topic: RL-Robotics
tags: [RL-Robotics, real-world-RL, multi-agent, critic-decomposition, human-in-the-loop, reward-shaping]
source: https://arxiv.org/abs/2608.09762
venue: "arXiv 2608.09762"
---

## Summary

This paper targets a specific scaling failure mode in real-world robot RL: prior sample-efficient, human-in-the-loop approaches only work with small domain-randomization ranges and break down when multiple robot actors are trained concurrently because of non-stationarity. It proposes a centralized-training/decentralized-execution (CTDE) framework where multiple physical actors share one centralized multi-head critic, decomposed into a sparse task-reward head and a potential-based grasping-reward head (Hybrid Reward Architecture), letting each actor act independently while training stays stable.

## Key Contributions

- Applies CTDE — well established in multi-agent RL — to the different problem of parallelizing single-task real-world robot RL across multiple physical actors/embodiments to increase real-world sample throughput.
- Hybrid Reward Architecture: decomposes the shared critic into a task head (sparse success reward) and a grasp head (dense potential-based reward), rather than hand-tuning a single scalar reward.
- Explicitly designed for sparse-reward manipulation with hybrid (discrete + continuous) action spaces and large domain randomization ranges — the regime where prior human-in-the-loop RL methods degrade.

## Strengths

- Tackles real-world (not just simulated) online RL, where sample efficiency and training stability are the actual bottlenecks to deployment, not benchmark performance.
- The critic decomposition is a lightweight, interpretable fix (grasp vs. task credit assignment) rather than a heavier reward-model or demonstration-based solution.
- Multi-actor centralized training directly addresses a wall-clock scaling problem: real robots are slow, and parallelizing collection across actors while keeping a single shared critic is a practical throughput lever.

## Weaknesses

- Applying CTDE to single-task multi-actor RL is a repurposing of an existing multi-agent RL idea rather than a fundamentally new technique — the novelty is in the application and reward decomposition, not the underlying credit-assignment machinery.
- Requires multiple physical robot actors running concurrently to get the throughput benefit, which is a significant hardware/lab-infrastructure requirement not every group can replicate.
- The two-head reward decomposition (task + grasp) is manipulation-specific; it's unclear how the architecture generalizes to tasks without a clean grasp sub-goal (e.g., locomotion, deformable-object manipulation).

## Open Questions

- How does the approach scale beyond a handful of actors, and does the shared-critic non-stationarity problem re-emerge at larger fleet sizes?
- Would the Hybrid Reward Architecture need a different decomposition for non-pick-and-place manipulation tasks?
- How much of the reported efficiency gain is attributable to CTDE versus simply having more physical robots collecting data in parallel?

## Significance

Real-world online RL for manipulation is notoriously sample-hungry; a reproducible recipe for scaling real-robot RL across multiple concurrent actors without retraining instability is directly relevant to labs trying to move human-in-the-loop RL from single-robot demos to fleet-scale training.

## Links

- [Paper](https://arxiv.org/abs/2608.09762)
