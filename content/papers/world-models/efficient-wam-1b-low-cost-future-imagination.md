---
title: "Efficient-WAM: A 1B-Parameter World-Action Model with Low-Cost Future Imagination"
date: 2026-06-11
topic: WorldModels
tags: [world-model, wam, efficiency, inference-speed, token-sparse, wan-2-2, real-time-deployment]
source: https://arxiv.org/abs/2606.10040
venue: "arXiv 2026"
---

## Summary

Existing WAMs achieve strong generalization through photorealistic future prediction but incur high inference latency, making real-time robot deployment impractical. Efficient-WAM treats future video prediction as a compact guidance signal rather than a visual fidelity target, using a video expert transferred from WAN-2.2-5B with token-sparse video latents and asymmetric video-action denoising that allocates fewer sampling steps to video than to actions. The 1B-parameter model reduces per-chunk latency to ~100 ms (30× speedup over existing WAMs) while maintaining competitive manipulation accuracy — key insight: visibly coarse futures still provide sufficient guidance for strong action generation.

## Key Contributions

- Compact video expert via knowledge transfer from WAN-2.2-5B to a 1B model
- Token-sparse video latents reducing computation without hurting action guidance
- Asymmetric video-action denoising: fewer steps for video, more for actions
- 30× wall-clock speedup (~100 ms per chunk) with competitive task accuracy

## Significance

Efficient-WAM provides the first empirical evidence that photorealistic video fidelity is not required for WAM benefits — coarse imagination is sufficient — which dramatically reduces the computational barrier to deploying WAMs on real hardware.

## Links

- [Paper](https://arxiv.org/abs/2606.10040)
