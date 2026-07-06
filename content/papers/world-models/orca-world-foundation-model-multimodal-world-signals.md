---
title: "Orca: The World is in Your Mind"
date: 2026-06-30
topic: WorldModels
tags: [WorldModels, world-foundation-model, multimodal, video-pretraining, embodied-AI, next-state-prediction]
source: https://arxiv.org/abs/2606.30534
venue: "ECCV 2026 / arXiv 2606.30534"
---

## Summary

Orca is a general world foundation model from the Beijing Academy of Artificial Intelligence (BAAI) that learns a unified world latent space from multimodal world signals. Instead of isolated next-token, next-frame, or next-action prediction, Orca focuses on Next-State-Prediction modeling via two complementary paradigms: unconscious learning from continuous videos and conscious learning from language-described events and VQA supervision. Pretrained on 125K hours of video and 160M event annotations, Orca outperforms specialized baselines at comparable scale across text generation, interactive image prediction, and embodied action generation.

## Key Contributions

- Unified world latent space learned from diverse multimodal world signals (video, language, events)
- Next-State-Prediction paradigm unifying understanding, prediction, and acting
- Unconscious learning (dense natural state transitions from video) + conscious learning (sparse meaningful transitions from language/VQA)
- Pretrained on 125K hours of video and 160M event annotations
- Accepted to ECCV 2026

## Significance

Orca demonstrates that a single world foundation model trained on diverse signals generalizes across text, image prediction, and embodied control—supporting the thesis that world modeling is a universal pretraining objective for physical AI.

## Links

- [Paper](https://arxiv.org/abs/2606.30534)
- [Project](https://orca-wm.github.io/)
