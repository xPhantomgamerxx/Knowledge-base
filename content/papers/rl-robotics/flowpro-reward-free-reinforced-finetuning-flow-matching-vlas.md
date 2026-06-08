---
title: "FlowPRO: Reward-Free Reinforced Fine-Tuning of Flow-Matching VLAs via Proximalized Preference Optimization"
date: 2026-06-03
topic: RL-Robotics
tags: [vla, reinforcement-fine-tuning, flow-matching, preference-optimization, reward-free, tencent-robotics]
source: https://arxiv.org/abs/2606.05468
venue: "arXiv 2606.05468"
---

## Summary

FlowPRO is a reward-free offline reinforced fine-tuning framework for flow-matching VLAs. It introduces RPRO (Robotic Flow-matching Proximalized Preference Optimization), a preference-optimization objective tailored to the continuous-action flow-matching head of VLA models, combining a contrastive optimizer with an explicit proximal regularizer that prevents reward-hacking.

## Key Contributions

- RPRO objective: extends preference optimization to the continuous trajectory space of flow-matching VLAs, avoiding the discrete-token assumptions of language-model DPO
- Proximal regularizer anchors the absolute magnitude of the implicit reward, eliminating the reward-hacking failure mode of plain Flow-DPO
- Reward-free formulation: no ground-truth reward labels needed — operates purely on preference pairs derived from offline data
- From Tencent Robotics X, Futian Laboratory, and Tsinghua University

## Significance

Solves a key gap in VLA post-training: how to do preference-based reinforcement fine-tuning when the action head is a continuous flow-matching model rather than a discrete token predictor, broadening RL-based improvement to the growing class of diffusion/flow VLAs.

## Links

- [Paper](https://arxiv.org/abs/2606.05468)
- [HTML](https://arxiv.org/html/2606.05468)
