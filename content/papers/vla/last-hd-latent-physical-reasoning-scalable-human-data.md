---
title: "LaST-HD: Learning Latent Physical Reasoning from Scalable Human Data for Robot Manipulation"
date: 2026-06-23
topic: VLA
tags: [VLA, human-robot-transfer, latent-reasoning, world-model-assisted, dexterous-manipulation, data-scaling]
source: https://arxiv.org/abs/2606.23685
venue: "arXiv 2606.23685"
---

## Summary

LaST-HD is a human-to-robot action learning paradigm that extends reasoning-before-acting VLA models by aligning human-hand and robot demonstrations in a shared latent reasoning space. An action-conditioned world model trained on unpaired human-hand and robot trajectories synthesizes unified latent targets, enabling the VLA to internalize shared physical dynamics without mimicking human kinematics. The paper also introduces the Out-of-Lab (OOL) Glove for scalable, low-cost human hand data collection.

## Key Contributions

- Shared latent reasoning space aligning human-hand and robot demonstrations via action-conditioned world model
- Trained on unpaired data (human and robot trajectories need not be synchronized)
- OOL Glove: low-cost motion-capture glove providing precise keypoints as universal action supervision across gripper types and dexterous hands
- Scalable data collection pipeline from human demonstrations to robot policy

## Significance

LaST-HD unlocks the vast pool of human-hand interaction data for robot learning without requiring embodiment-matched demonstrations, substantially lowering the cost of data collection for dexterous manipulation.

## Links

- [Paper](https://arxiv.org/abs/2606.23685)
- [Project](https://siriyep.github.io/last-hd-project-page/)
