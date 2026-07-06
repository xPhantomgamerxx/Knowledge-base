---
title: "Neuro-Symbolic Safety Guidance for Vision-Language-Action Models via Constrained Flow Matching"
date: 2026-07-01
topic: VLA
tags: [VLA, safety, flow-matching, neuro-symbolic, collision-avoidance, safe-robotics]
source: https://arxiv.org/abs/2607.01378
venue: "arXiv 2607.01378"
---

## Summary

Existing VLA safety measures only prevent collisions caused by the robot's immediately next action, which is insufficient for flow-matching VLAs that determine actions by predicting a full trajectory through iterative neural flow matching. This paper introduces a neuro-symbolic safety guidance mechanism that integrates symbolic safety constraints directly into the flow matching process, enabling predictive collision avoidance across the entire trajectory horizon.

## Key Contributions

- Neuro-symbolic safety guidance embedded within the iterative flow matching inference process
- Predictive collision avoidance over the entire action trajectory, not just the next action
- Compatible with existing flow-matching VLA backbones without retraining
- Formal safety guarantees through constrained optimization during inference

## Significance

The first safety framework designed specifically for the trajectory-level inference of flow-matching VLAs, enabling safe deployment in environments with dynamic obstacles without compromising task performance.

## Links

- [Paper](https://arxiv.org/abs/2607.01378)
