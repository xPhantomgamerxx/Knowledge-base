---
title: "VLA-Corrector: Lightweight Detect-and-Correct Inference for Adaptive Action Horizon"
date: 2026-07-01
topic: VLA
tags: [vla, inference, action-chunking, action-horizon, closed-loop, error-correction, eccv]
source: https://arxiv.org/abs/2607.01804
venue: "arXiv 2607.01804 / ECCV 2026"
---

## Summary

VLA-Corrector addresses the "predict-then-blindly-execute" failure mode of action-chunked VLAs by adding a lightweight Latent-space Vision Monitor (LVM) that detects when predicted visual dynamics diverge from actual observations. When a mismatch is detected, it truncates stale actions and triggers corrective replanning via Online Gradient Guidance (OGG) — all without modifying or retraining the VLA backbone.

## Key Contributions

- Latent-space Vision Monitor (LVM): continuously compares predicted vs. actual visual feature trajectories to detect execution drift
- Online Gradient Guidance (OGG): corrective replanning mechanism that engages when the LVM flags a mismatch
- Event-triggered adaptive action horizon: long-horizon execution preserved when reliable; short-horizon correction invoked when drift is detected
- Drop-in compatible with any action-chunked VLA (tested on PI0.5, SmolVLA); builds on LeRobot ecosystem

## Significance

Closes the reactivity gap in action-chunked VLAs for contact-rich manipulation without architectural changes, substantially reducing compounding errors in long-horizon tasks — the key failure mode of fixed-horizon open-loop execution.

## Links

- [Paper](https://arxiv.org/abs/2607.01804)
- [Project Page](https://zju-omniai.github.io/vla-corrector/)
- [GitHub](https://github.com/ZJU-OmniAI/vla-corrector)
