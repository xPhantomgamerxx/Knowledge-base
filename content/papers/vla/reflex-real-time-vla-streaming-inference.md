---
title: "Reflex: Real-Time VLA Control through Streaming Inference"
date: 2026-07-18
topic: VLA
tags: [vla, real-time, streaming, inference-efficiency, latency, control-frequency, icml]
source: https://arxiv.org/abs/2607.14695
venue: "arXiv 2607.14695 / ICML 2026"
---

## Summary

Reflex introduces streaming inference for vision-language-action models, enabling real-time robot control at much higher control frequencies than standard VLA generation pipelines. By reformulating VLA generation as an incremental streaming process rather than a full-sequence generation step, Reflex decouples inference latency from action-chunk length and allows the robot to begin executing the earliest tokens of an action sequence before generation is complete.

## Key Contributions

- Streaming inference formulation: VLA outputs are consumed incrementally as they are generated, eliminating the full-sequence generation bottleneck
- Enables real-time VLA control frequencies compatible with high-speed manipulation tasks
- Accepted at ICML 2026, providing strong peer-reviewed validation of the approach
- Addresses the fundamental latency-capability tradeoff in deploying large VLA models for reactive robot control

## Significance

ICML 2026 acceptance for a core VLA inference efficiency paper signals mainstream recognition of the real-time deployment gap — Reflex offers a principled streaming solution that does not sacrifice model capability for speed, potentially enabling a new class of reactive foundation-model-based robot controllers.

## Links

- [Paper](https://arxiv.org/abs/2607.14695)
