---
title: "Towards Efficient Robotic Manipulation Models with Self-Recursive Pruning"
date: 2026-10-06
topic: VLA
tags: [vla, model-compression, efficient-vla, robotics]
source: https://arxiv.org/abs/2610.08555
venue: "arXiv"
---

## Summary

This paper proposes a training-free, unstructured pruning method ("LCAM") for compressing pretrained robotic manipulation policies like OpenVLA, applied recursively to progressively remove weights without retraining. At 50% pruning on LIBERO-Object with OpenVLA, it reports retaining 84.0% success (over 90% of the dense policy's performance), and 68.5% success at 60% pruning.

## Key Contributions

- A training-free, self-recursive unstructured pruning scheme (LCAM) for VLA-style manipulation policies.
- Demonstrated retention of over 90% of dense-model success at 50% weight pruning on LIBERO-Object with OpenVLA.
- A second pruning level (60%) reported to show the degradation curve as compression increases.

## Strengths

- Training-free compression is attractive operationally: no need for a retraining pass or access to the original training data/pipeline to compress an already-deployed model.
- Retaining over 90% of original performance at 50% pruning is a strong compression ratio if it generalizes beyond LIBERO-Object.

## Weaknesses

- Evaluated specifically on LIBERO-Object (a subset of LIBERO) with OpenVLA; broader task-suite and cross-architecture generalization isn't established in the available material.
- Training-free pruning methods often show steeper degradation outside the specific benchmark they were tuned/validated on; this isn't addressed here.

## Open Questions

- How does LCAM compare directly to other recent action-aware pruning/distillation methods (VLA-ACL, SpecPrune-VLA, ActDistill) under matched conditions?
- Does the pruning approach generalize to non-OpenVLA architectures (diffusion/flow-based action heads, for instance)?

## Significance

Another entry in the increasingly crowded but practically important efficient-VLA compression literature, notable mainly for being training-free, which lowers the barrier to compressing already-trained, deployed policies.

## Links

- [Paper](https://arxiv.org/abs/2610.08555)
