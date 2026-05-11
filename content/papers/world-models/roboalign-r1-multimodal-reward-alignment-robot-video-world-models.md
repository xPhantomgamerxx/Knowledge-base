---
title: "RoboAlign-R1: Distilled Multimodal Reward Alignment for Robot Video World Models"
date: 2026-05-05
topic: WorldModels
tags: [reward-alignment, video-world-model, GRPO, RL-post-training, long-horizon, benchmark]
source: https://arxiv.org/abs/2605.03821
venue: "arXiv 2605.03821"
---

## Summary

RoboAlign-R1 addresses the mismatch between standard pixel-reconstruction training objectives and what actually matters for robot decision-making in video world models. It constructs RobotWorldBench (10,000 annotated video-instruction pairs), trains a multimodal teacher judge (RoboAlign-Judge) for six-dimensional video evaluation, and distills it into a lightweight student reward model used for GRPO-based RL post-training of world models.

## Key Contributions

- RobotWorldBench: 10k annotated video-instruction pairs from four robot data sources for fine-grained world model evaluation
- RoboAlign-Judge: multimodal teacher scoring instruction following, manipulation success, and physical plausibility across six dimensions
- GRPO-based RL post-training using the distilled student reward model to align world model outputs with decision-relevant quality
- Sliding-window re-encoding strategy to stabilize long-horizon autoregressive rollouts and reduce error accumulation

## Significance

Establishes a principled reward-alignment pipeline for robot video world models, bridging the gap between low-level reconstruction objectives and high-level task success metrics needed for planning.

## Links

- [Paper](https://arxiv.org/abs/2605.03821)
- [HTML](https://arxiv.org/html/2605.03821)
