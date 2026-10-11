---
title: "Devol-ONE: One Autoregressive Mixture of Transformers to Unify Vision-Language-Action and Latent World Modeling"
date: 2026-09-26
topic: VLA
tags: [vla, world-models, architecture, robotics]
source: https://arxiv.org/abs/2609.32193
venue: "arXiv"
---

## Summary

Devol-ONE unifies vision-language understanding, latent future-state prediction, and action generation inside a single Mixture-of-Transformers model with three parameter-disjoint streams (VL, dynamics, and a diffusion action expert), with the dynamics stream initialized from a V-JEPA backbone and trained with a new "Autoregressive Latent Rollout Training" scheme. It reports 98.4% average success on LIBERO and 71.4% zero-shot on the harder LIBERO-Plus perturbation suite without any fine-tuning on perturbed data.

## Key Contributions

- A single autoregressive Mixture-of-Transformers architecture that couples VLA control with latent world modeling rather than training them as separate systems.
- Initialization of the dynamics stream from a pretrained V-JEPA representation, reusing strong self-supervised video features for future-state prediction.
- "Autoregressive Latent Rollout Training," a scheme for jointly training the dynamics and action streams over rolled-out latent trajectories.

## Strengths

- Strong zero-shot robustness number on LIBERO-Plus (71.4%) suggests that baking world-model-style future prediction into the backbone helps generalization beyond the perturbation-free benchmark, not just raw task success.
- Parameter-disjoint streams give some interpretability/modularity compared to a single monolithic transformer doing everything.
- Evaluated on both simulation (LIBERO, RoboTwin 2.0) and two different real-robot setups (Flexiv single- and dual-arm).

## Weaknesses

- Three-stream Mixture-of-Transformers design adds architectural and training complexity relative to single-stream VLA baselines.
- Reliance on a pretrained V-JEPA backbone ties performance partly to the quality of that external component.
- No ablation reported (in available material) isolating how much of the LIBERO-Plus robustness comes from the world-model stream versus the action expert or training scheme.

## Open Questions

- How sensitive are the reported gains to the choice and quality of the pretrained V-JEPA initialization?
- Does the added dynamics stream meaningfully increase inference cost relative to pure-action VLA baselines, and is it worth the tradeoff for real-time control?

## Significance

Reflects the field's continuing convergence of VLA and world-model research threads (echoing WorldVLA, LingBot-VA) into single architectures that jointly reason about "what will happen" and "what to do," which is a plausible path to better out-of-distribution robustness.

## Links

- [Paper](https://arxiv.org/abs/2609.32193)
