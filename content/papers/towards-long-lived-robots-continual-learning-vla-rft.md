---
title: "Towards Long-Lived Robots: Continual Learning VLA Models via Reinforcement Fine-Tuning"
date: 2026-02-11
topic: RL-Robotics
tags: [continual-learning, reinforcement-fine-tuning, catastrophic-forgetting, VLA, LifeLong-RFT, MDPR]
source: https://arxiv.org/abs/2602.10503
venue: "arXiv"
---

## Summary

LifeLong-RFT addresses the catastrophic forgetting problem in VLA models when supervised fine-tuning (SFT) is applied to new downstream tasks. The proposed Reinforcement Fine-Tuning strategy is independent of online environmental feedback and pre-trained reward models, instead using chunking-level on-policy RL with a Multi-Dimensional Process Reward (MDPR) that quantifies the heterogeneous contributions of intermediate action chunks across three dimensions to facilitate stable policy optimization.

## Key Contributions

- LifeLong-RFT: RFT strategy that requires no online environmental feedback or external reward models
- Multi-Dimensional Process Reward (MDPR) for evaluating action chunks along multiple quality dimensions
- Chunking-level on-policy RL adapted to the autoregressive action-chunk structure of VLAs
- Mitigates catastrophic forgetting while substantially reducing task-specific data requirements vs SFT

## Significance

LifeLong-RFT addresses a critical practical challenge for deploying VLAs in dynamic real-world settings: how to adapt to new tasks without regressing on previously learned skills, without incurring the cost of online data collection or external reward engineering.

## Links

- [arXiv](https://arxiv.org/abs/2602.10503)
- [HTML version](https://arxiv.org/html/2602.10503)
