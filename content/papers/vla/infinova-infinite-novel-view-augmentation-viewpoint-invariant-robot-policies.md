---
title: "InfiNoVA: Infinite Novel View Augmentation for Viewpoint Invariant Robot Policies"
date: 2026-09-23
topic: VLA
tags: [vla, data-augmentation, synthetic-data, robotics, vla-posttraining]
source: https://arxiv.org/abs/2609.27734
venue: "arXiv / 4th TPC Workshop @ SC'26"
---

## Summary

InfiNoVA converts synchronized multi-camera robot demonstrations into a 3D Gaussian-splat representation and renders a dense distribution of new, geometrically consistent camera viewpoints, turning a handful of fixed-camera demos into a much larger set of viewpoint-augmented training examples. Policies trained on this augmented data report 5.4x higher average success than both an unaugmented policy and a prior novel-view-synthesis baseline (VISTA) under unseen, randomized camera viewpoints.

## Key Contributions

- A pipeline that reconstructs demonstrations as 3D Gaussian splats and renders them from arbitrary novel viewpoints for training-data augmentation.
- Comparison against several generative/3D baselines (VISTA, GLD, Hunyuan3D, DepthSplat), with most judged unrealistic or too costly for downstream policy training.
- Evaluation of a SmolVLA-based policy under unseen randomized viewpoints after augmentation.

## Strengths

- Directly targets a well-known brittleness of imitation-learned policies: sensitivity to camera placement.
- Keeps the downstream policy architecture unchanged, making the method a drop-in data pipeline rather than a new model.
- Large reported robustness gain (5.4x) against a reasonably strong existing augmentation baseline (VISTA).

## Weaknesses

- Reconstruction quality (and therefore augmentation quality) depends on having good multi-camera coverage of the original demonstrations.
- Gaussian-splat reconstruction and rendering add a non-trivial offline compute cost per demonstration.
- Evaluated with one base policy (SmolVLA); generality to other VLA backbones is untested in the available material.

## Open Questions

- How well does the splat-based augmentation handle dynamic scenes with moving objects, versus the largely static scenes implied by synchronized multi-camera capture?
- Does the benefit persist at larger pretraining data scale, where viewpoint diversity may already be present?

## Significance

Viewpoint robustness is a persistent failure mode for real-world VLA deployment (robots get bumped, cameras get remounted, new robots have different mounts), so a general-purpose, policy-agnostic augmentation pipeline that measurably improves viewpoint generalization is directly useful for scaling data collection without new physical demos.

## Links

- [Paper](https://arxiv.org/abs/2609.27734)
