---
title: "Bridging the Morphology Gap: Adapting VLA Models to Dexterous Manipulation via Intent-Conditioned Fine-Tuning"
date: 2026-06-10
topic: VLA
tags: [vla, fine-tuning, dexterous-manipulation, cross-embodiment, vla-posttraining]
source: https://arxiv.org/abs/2606.12109
venue: "arXiv"
---

## Summary

This paper addresses adapting VLA models pretrained on low-DoF parallel-gripper data to high-DoF dexterous hands — a transfer that normally causes catastrophic forgetting of spatial reasoning and action-manifold collapse when dexterous-hand data is scarce. It introduces "InDex," which repurposes the pretrained model's 1-DoF parallel-grasp output as a continuous virtual grasp-intent proxy to sequentialize the dexterous control topology.

## Key Contributions

- Identifies and names a specific, previously under-characterized failure mode: fine-tuning a low-DoF-pretrained VLA directly on high-DoF dexterous data causes action-manifold collapse under data scarcity.
- InDex reuses the pretrained parallel-grasp output as a continuous intent signal rather than discarding it, giving the dexterous fine-tuning process a structured scaffold instead of learning the full high-DoF mapping from scratch.
- Framed explicitly as a data-efficient fine-tuning method for morphology transfer, relevant to any lab wanting to move a pretrained low-DoF VLA onto dexterous hardware without collecting a full new dexterous dataset.

## Strengths

- The "virtual grasp-intent proxy" idea is a clever reuse of existing pretrained capability rather than requiring new pretraining data or architecture changes, which lowers the practical barrier to adoption.
- Directly targets a real and common problem for labs deploying VLAs originally trained on simpler grippers onto dexterous hands.

## Weaknesses

- The approach is architecturally coupled to models whose pretrained output includes a meaningful parallel-grasp signal; it's unclear how it would apply to VLAs pretrained without such an action head.
- "Sequentializing the dexterous control topology" via a scalar intent proxy could lose fine-grained multi-finger coordination information that dexterous tasks (e.g. in-hand reorientation) specifically require — the paper's task selection for evaluation is not detailed in available coverage.

## Open Questions

- Does the intent-conditioned scaffold generalize to hands with substantially different kinematic structure (e.g. tendon-driven vs. fully actuated), or is it tuned to a specific dexterous hand used in the experiments?
- How does InDex compare against directly co-training on a small dexterous dataset from scratch, rather than adapting a frozen low-DoF pretrained model?

## Significance

A targeted contribution to the practical problem of morphology transfer for VLAs, relevant as dexterous hands (e.g. the 1X NEO hand already logged in this vault) become more common deployment targets for models originally pretrained on simpler end-effectors.

## Links

- [Paper](https://arxiv.org/abs/2606.12109)
