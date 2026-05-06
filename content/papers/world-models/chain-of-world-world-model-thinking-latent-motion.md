---
title: "Chain of World: World Model Thinking in Latent Motion"
date: 2026-03-01
topic: WorldModels
tags: [chain-of-thought, latent-motion, video-VAE, VLA-pretraining, CVPR-2026, visuomotor, disentangled-representation]
source: https://arxiv.org/abs/2603.03195
venue: "CVPR 2026"
---

## Summary

CoWVLA introduces the "Chain of World" paradigm that unifies world-model temporal reasoning with a disentangled latent motion representation for VLA pretraining. A pretrained video VAE factorizes video segments into structure and motion latents; the model then learns to infer a continuous latent motion chain from instruction and initial frame, predicting the terminal frame as a world model goal. At co-fine-tuning, these latent dynamics are aligned with discrete action prediction via a unified autoregressive decoder that jointly models sparse keyframes and actions.

## Key Contributions

- Chain of World paradigm: continuous latent motion chains as intermediate world-model reasoning steps for VLAs
- Pretrained video VAE for disentangled structure and motion latent factorization
- Pre-training objective: latent motion chain inference + terminal frame prediction from instruction and initial frame
- Co-fine-tuning: joint keyframe and action modeling in a unified autoregressive decoder
- Accepted at CVPR 2026; outperforms existing world-model and latent-action approaches on robotic simulation benchmarks

## Significance

CoWVLA preserves the rich temporal knowledge of world models while avoiding the high computational cost of pixel-space generation, making world-model-based VLA pretraining practical and efficient.

## Links

- [Paper](https://arxiv.org/abs/2603.03195)
- [GitHub](https://github.com/fx-hit/CoWVLA)
