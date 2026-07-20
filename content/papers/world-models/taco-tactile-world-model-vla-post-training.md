---
title: "TACO: TActile World Model as a Self-COrrector for Scalable VLA Post-Training"
date: 2026-07-03
topic: WorldModels
tags: [world-model, tactile, vla, post-training, contact-rich, visuo-tactile, data-synthesis]
source: https://arxiv.org/abs/2607.02840
venue: "arXiv 2607.02840"
---

## Summary

TACO is a tactile-aware world-model framework for scalable VLA post-training in contact-rich manipulation. It uses a Recognize–Imagine–Label loop: real-world failure-adjacent states are recognized, a visuo-tactile world model imagines local correction segments (joint RGB+force denoising), and corrective actions are labeled for VLA post-training — converting failures into self-supervised supervisory signal.

## Key Contributions

- Visuo-tactile generation model: jointly denoises video frames and force trajectories for local correction segment synthesis
- Unified progress-action model: estimates task progress and predicts corrective actions from generated segments
- Recognize–Imagine–Label loop: closes the failure-to-correction pipeline with no human annotation
- Scalable post-training: generates corrective supervision from real-world failures without large-scale tactile pretraining datasets

## Significance

Bridges the gap between rich tactile sensing and VLA post-training by turning contact failures into training data automatically — a scalable route to contact-rich manipulation that does not require purpose-built tactile pretraining corpora.

## Links

- [Paper](https://arxiv.org/abs/2607.02840)
