---
title: "PolicyTrim: Boosting Intrinsic Policy Efficiency of Vision-Language-Action Models"
date: 2026-06-26
topic: VLA
tags: [efficiency, inference-speed, rl-post-training, action-chunking, pruning]
source: https://arxiv.org/abs/2606.22540
venue: "arXiv 2606.22540"
---

## Summary

PolicyTrim is a two-stage RL post-training framework that reduces VLA inference steps without architectural modifications or additional demonstration data. Stage 1 uses dynamic horizon exploration to push the trustworthy prediction frontier toward its empirical limit; Stage 2 applies redundancy-aware reward and group-anchored stability regularization to drive the policy toward genuinely concise execution while maintaining task competence.

## Key Contributions

- Dynamic horizon exploration mechanism in Stage 1 that progressively extends the action-chunk prediction horizon to find the practical limit for each policy and task
- Redundancy-aware reward in Stage 2 that penalizes unnecessary action steps, combined with group-anchored stability regularization to prevent performance collapse during compression
- Architecture-agnostic: demonstrated across diverse backbones and benchmarks without additional demonstrations or model changes

## Significance

Addresses inference efficiency as a critical deployment bottleneck for VLAs through principled RL, achieving significant reductions in inference frequency while maintaining strong task success rates — an important step toward real-time robot deployment.

## Links

- [Paper](https://arxiv.org/abs/2606.22540)
