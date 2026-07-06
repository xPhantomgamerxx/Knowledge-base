---
title: "LoopVLA: Learning Sufficiency in Recurrent Refinement for Vision-Language-Action Models"
date: 2026-05-09
topic: VLA
tags: [VLA, efficiency, recurrent-transformer, test-time-compute, inference-optimization, action-chunking]
source: https://arxiv.org/abs/2605.09948
venue: "arXiv 2605.09948"
---

## Summary

LoopVLA replaces the conventional fixed-depth Transformer in VLA models with a shared looped Transformer that enables progressive refinement of representations. A dual-head design with an action head and a sufficiency head allows the model to learn when to stop iterating, reducing model size by 45% while maintaining strong performance.

## Key Contributions

- Shared looped (recurrent) Transformer replaces fixed-depth backbone for VLA representation learning
- Distribution alignment objective for learning sufficiency estimation from action optimization signals
- Dual-head design (action + sufficiency) enables learned early-exit without heuristic criteria
- 45% model size reduction; up to 1.7× higher inference throughput in extreme settings
- Evaluated on LIBERO, LIBERO-Plus, and VLA-Arena

## Significance

LoopVLA shows that recurrent computation with adaptive depth achieves competitive VLA performance at substantially lower parameter count and latency, making real-time deployment on resource-constrained hardware more feasible.

## Links

- [Paper](https://arxiv.org/abs/2605.09948)
