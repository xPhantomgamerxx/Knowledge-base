---
title: "RynnWorld-4D: 4D Embodied World Models for Robotic Manipulation"
date: 2026-07-08
topic: WorldModels
tags: [4d-world-model, depth, optical-flow, alibaba, diffusion, bimanual, sim2real]
source: https://arxiv.org/abs/2607.06559
venue: "arXiv 2607.06559"
---

## Summary

RynnWorld-4D co-generates future RGB frames, depth maps, and optical flow from a single RGB-D image and a text instruction in one shared denoising loop. A tri-branch architecture with cross-modal attention and frame-wise 3D RoPE captures both geometric structure and motion dynamics simultaneously. The companion Rynn4DDataset 1.0 provides 254.4 million frames with pseudo-labeled depth and optical flow across egocentric human and robot manipulation videos.

## Key Contributions

- Tri-branch diffusion Transformer that co-generates RGB, depth (D), and optical flow (F) within one denoising process, using cross-modal attention so each modality informs the others
- Frame-wise 3D RoPE encoding that preserves spatial-temporal structure across the joint generation manifold
- RynnWorld-4D-Policy: mid-diffusion policy head that extracts 4D internal representations for high-frequency, closed-loop bimanual control with effective zero-shot Sim2Real transfer

## Significance

First world model to unify RGB, depth, and optical-flow generation in a single denoising loop, providing explicit geometric and motion cues that improve downstream policy learning on complex bimanual manipulation tasks.

## Links

- [Paper](https://arxiv.org/abs/2607.06559)
- [Alibaba tech coverage](https://www.techtimes.com/articles/319971/20260709/alibaba-robot-world-model-predicts-geometry-motion-before-each-move.htm)
