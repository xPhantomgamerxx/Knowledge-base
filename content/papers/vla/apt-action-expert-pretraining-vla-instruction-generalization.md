---
title: "APT: Action Expert Pretraining Improves Instruction Generalization of Vision-Language-Action Policies"
date: 2026-06-10
topic: VLA
tags: [VLA, instruction-generalization, action-pretraining, language-grounding, imitation-learning]
source: https://arxiv.org/abs/2606.12366
venue: "arXiv 2606.12366"
---

## Summary

VLA models coupling pretrained VLMs with continuous action experts show strong manipulation performance but generalize poorly to out-of-distribution language instructions due to structural imbalance in training data (language is far less diverse than visual and action content). APT factorizes the policy into a language-agnostic Vision-Action (VA) prior and a language-conditioned VLA likelihood, training the action expert first on vision-action pairs before injecting language through a gated fusion mechanism.

## Key Contributions

- Bayesian factorization of VLA policy into VA prior and language-conditioned likelihood
- Stage 1: Action expert pretraining on vision-action pairs with frozen VLM, bypassing language imbalance
- Stage 2: Language tokens injected via gated fusion that integrates VLM features while preserving the visuomotor prior
- Consistent gains on unseen instructions and compositional tasks across multiple benchmarks

## Significance

APT directly addresses the language generalization gap in VLA models from first principles, offering a training recipe that does not require additional data collection—only a changed training order and fusion architecture.

## Links

- [Paper](https://arxiv.org/abs/2606.12366)
