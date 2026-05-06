---
title: "What Matters for Simulation to Online Reinforcement Learning on Real Robots"
date: 2026-02-23
topic: RL-Robotics
tags: [sim-to-real, online-RL, real-robot, design-choices, ablation, multi-platform, recipe]
source: https://arxiv.org/abs/2602.20220
venue: "arXiv"
---

## Summary

This empirical study systematically ablates algorithmic, systems, and experimental design choices for sim-to-online RL on physical robots across 100 real-world training runs on three distinct robotic platforms. The work identifies that several widely adopted defaults are actually harmful, and that a small set of principled choices — retaining data across real-world trials and delaying critic updates — yield stable, reliable online RL without extensive engineering overhead.

## Key Contributions

- Comprehensive 100-run ablation of design choices for sim-to-online RL across three real robot platforms
- Identifies harmful defaults in standard RL practice that degrade real-robot performance
- Key recipe: retain cross-trial data replay buffer + delay critic updates for stability
- Actionable, hardware-agnostic guidelines that reduce the engineering barrier for deploying online RL on real robots
- Empirical study bridging the sim-to-online gap with practical, reproducible findings

## Significance

By grounding design choices in large-scale real-robot experiments rather than simulation benchmarks, this work provides the community with a reliable starting recipe for online RL deployment — directly addressing the reproducibility gap in real-world robot learning.

## Links

- [Paper](https://arxiv.org/abs/2602.20220)
