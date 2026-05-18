---
title: "DeFI: Disentangled Robot Learning via Separate Forward and Inverse Dynamics Pretraining"
date: 2026-03-27
topic: VLA
tags: [pretraining, forward-dynamics, inverse-dynamics, action-free-video, ICLR-2026]
source: https://arxiv.org/abs/2604.16391
venue: "ICLR 2026"
---

## Summary

DeFI addresses the entanglement problem in VLA training—where 2D image forecasting and 3D action prediction are jointly optimized yet pull in conflicting directions—by pretraining a General Forward Dynamics Model (GFDM) on diverse human and robot videos for future prediction and a separate General Inverse Dynamics Model (GIDM) via self-supervised learning from unlabeled video transitions. Both components are then integrated into a unified architecture for end-to-end fine-tuning.

## Key Contributions

- Decouples visual world-model pretraining (GFDM) from action inference (GIDM), enabling exploitation of large-scale action-free web video
- GIDM infers latent actions from unlabeled video transitions via self-supervised contrastive learning
- State-of-the-art on CALVIN (avg. task length 4.51), 51.2% on SimplerEnv-Fractal, and 81.3% real-world success rate

## Significance

Published at ICLR 2026, DeFI shows that disentangling visual future prediction from action inference is both principled and practically powerful, substantially improving generalization across sim and real-world robot manipulation benchmarks.

## Links

- [Paper](https://arxiv.org/abs/2604.16391)
- [GitHub](https://github.com/LogosRoboticsGroup/DeFi)
