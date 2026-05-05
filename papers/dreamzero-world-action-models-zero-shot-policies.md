---
title: "World Action Models are Zero-shot Policies (DreamZero)"
date: 2026-02-17
topic: WorldModels
tags: [world-model, zero-shot, cross-embodiment, video-diffusion, WAM, generalization]
source: https://arxiv.org/abs/2602.15922
venue: "arXiv"
---

## Summary

DreamZero introduces the World Action Model (WAM) architecture — built on a pretrained video diffusion backbone — that jointly models future world states as video and robot actions. Unlike VLAs that learn semantic mappings, WAMs learn physical dynamics directly from diverse robot data without repetitive demonstrations. Real robot experiments show over 2x improvement in generalization to new tasks and environments compared to state-of-the-art VLAs.

## Key Contributions

- World Action Model (WAM): jointly predicts future video frames and robot actions via video diffusion
- Zero-shot generalization to unseen tasks and environments by learning physical dynamics
- Effective learning from heterogeneous robot datasets without repetitive demonstrations
- Cross-embodiment transfer capability without embodiment-specific architectures

## Significance

DreamZero challenges the dominant VLA paradigm by demonstrating that world-model-based architectures generalize substantially better than language-conditioned policies in novel physical settings. Its adoption by NVIDIA as the basis for GR00T N2 signals that world action models may become the next dominant paradigm for robot foundation models.

## Links

- [arXiv](https://arxiv.org/abs/2602.15922)
- [Project Page](https://dreamzero0.github.io/)
