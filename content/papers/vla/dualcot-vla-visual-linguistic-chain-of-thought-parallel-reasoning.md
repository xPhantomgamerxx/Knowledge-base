---
title: "DualCoT-VLA: Visual-Linguistic Chain of Thought via Parallel Reasoning for Vision-Language-Action Models"
date: 2026-03-23
topic: VLA
tags: [chain-of-thought, parallel-reasoning, spatial-understanding, task-planning, LIBERO, RoboCasa, HKUST]
source: https://arxiv.org/abs/2603.22280
venue: "arXiv"
---

## Summary

DualCoT-VLA addresses two failure modes in standard VLA models: inability to simultaneously capture fine-grained spatial details (low-level) and logical task structure (high-level), and high inference latency from step-by-step autoregressive CoT decoding. The method combines a Visual CoT for spatial understanding with a Linguistic CoT for task planning, and replaces sequential autoregressive reasoning with a parallel mechanism using learnable query tokens that complete both CoT paths in a single forward pass.

## Key Contributions

- Dual-modal CoT: Visual CoT branch for low-level spatial understanding, Linguistic CoT branch for high-level planning
- Parallel CoT mechanism with two sets of learnable query tokens, collapsing multi-step autoregressive reasoning to a single forward pass
- Eliminates compounding errors from sequential CoT decoding while preserving reasoning quality
- State-of-the-art results on LIBERO and RoboCasa GR1 benchmarks plus real-robot platforms

## Significance

DualCoT-VLA resolves the latency-vs-reasoning trade-off that has limited prior CoT-based VLAs, making dual-modal chain-of-thought practical for real-time robot deployment.

## Links

- [Paper](https://arxiv.org/abs/2603.22280)
