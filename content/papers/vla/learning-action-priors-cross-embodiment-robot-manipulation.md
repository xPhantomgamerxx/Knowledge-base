---
title: "Learning Action Priors for Cross-embodiment Robot Manipulation"
date: 2026-06-26
topic: VLA
tags: [VLA, cross-embodiment, action-prior, flow-matching, pretraining, generalization]
source: https://arxiv.org/abs/2606.26095
venue: "arXiv 2606.26095"
---

## Summary

Current VLA models leave the action module to learn physical motion from scratch during joint training, requiring simultaneous discovery of temporal action dynamics and cross-modal alignment—a challenge amplified in cross-embodiment settings. This work pretains the action module with motion priors before cross-modal VLA alignment via a two-stage framework: Stage 1 learns temporal motion structure from action trajectories alone using a flow-matching encoder-decoder (no visual/language tokens); Stage 2 transfers the prior to VLA training via decoder reuse and early-stage latent distillation.

## Key Contributions

- Decoupled two-stage training: motion prior pretraining then cross-modal VLA alignment
- Stage 1: Lightweight flow-matching encoder-decoder learns temporal structure from unconditioned action trajectories
- Stage 2: Learned encoder used as compact history compressor, summarizing state-action histories into a single temporal context token
- Designed for cross-embodiment generalization with heterogeneous action distributions

## Significance

Giving the VLA action module an explicit motion prior before cross-modal training reduces the simultaneous optimization burden and yields better cross-embodiment transfer with less data.

## Links

- [Paper](https://arxiv.org/abs/2606.26095)
