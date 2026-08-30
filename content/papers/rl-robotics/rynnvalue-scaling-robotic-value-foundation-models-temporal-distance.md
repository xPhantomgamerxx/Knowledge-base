---
title: "RynnValue: Scaling Robotic Value Foundation Models with Temporal Distance"
date: 2026-08-10
topic: RL-Robotics
tags: [vla-posttraining, value-foundation-model, reward-model, temporal-distance, offline-to-online-rl]
source: https://arxiv.org/abs/2608.09853
venue: "arXiv"
---

## Summary

RynnValue, from Alibaba DAMO Academy (Dongchi Huang, Hongyin Zhang, Bohan Hou, Siteng Huang, et al.), is a value foundation model built on the RynnBrain/Qwen3-VL backbone that predicts "temporal distance" — the directed, signed cost-to-go in seconds from an observation to a language-specified goal — as a label-free supervision signal learned purely from timestamps. Because temporal-distance labels require no manual preference or progress annotation, the model scales to over 7,000 hours (~3M instruction-conditioned clips) of heterogeneous embodied data spanning multiple embodiments and data sources, and the resulting value model is then used to derive dense potential-based rewards for RL fine-tuning of downstream manipulation policies.

## Key Contributions

- Replaces task-internal supervision anchors (human preferences, hand-normalized task progress) — which don't transfer across embodiments/datasets — with temporal distance, a signal derivable directly and cheaply from video timestamps at massive scale.
- An architecture with grouped absolute/relative temporal-distance query tokens plus a value-isolation attention mechanism that prevents different query groups from attending to each other, explicitly designed to suppress shortcut learning that would otherwise make predictions insensitive to actual task failures/regressions.
- Training recipe safeguards (random temporal sampling, temporal-order shuffling, ~10% instruction-mismatch augmentation) targeted at forcing the model to ground its temporal-distance predictions in genuine visual/task evidence rather than superficial video statistics.
- Demonstrates the value model can be converted into dense potential-based-shaping rewards that measurably improve downstream RL fine-tuning of real-world manipulation policies: 52.5%→72.5% success online and 63.8%→82.5% offline on real dual-arm (Franka) tasks.
- Achieves state-of-the-art policy-ranking performance (Kendall's τₐ = 0.675 on RBM-EVAL-OOD) without any preference supervision, beating a fully preference-supervised baseline (0.655) and more than doubling a progress-only counterpart (0.292), while generalizing zero-shot to unseen tasks, embodiments, and viewpoints.

## Strengths

- The core insight — that timestamps are a free, universally-available supervision signal across heterogeneous datasets — is a genuinely scalable alternative to preference labels, which are expensive and don't transfer well across embodiments.
- Explicit anti-shortcut engineering (value-isolation attention, order shuffling, instruction-mismatch augmentation) shows the authors anticipated and tested for a real failure mode of temporal-distance learning (models learning to count frames instead of understanding task semantics), rather than assuming scale alone would fix it.
- Real-world validation on dual-arm manipulation with concrete before/after RL fine-tuning success-rate numbers is far stronger evidence than offline ranking metrics alone.
- Beating a preference-supervised SOTA baseline while using zero preference labels is a strong scaling argument: it suggests supervision cost, not model capacity, was the bottleneck for prior value/reward models.
- Open-sourced (GitHub, HuggingFace, ModelScope), which lowers the barrier for the community to build on it as a reward/value backbone for RL fine-tuning of generalist policies.

## Weaknesses

- Temporal distance is a proxy for task progress, but it conflates "time elapsed" with "progress made" — a demonstration with unnecessary dwelling/idle time or a subtly failed-then-recovered trajectory could distort the ground-truth timestamp label the model is trained on, without any correction mechanism described for such quality issues in the underlying 7,000+ hours of data.
- The reported real-world gains (52.5%→72.5%, 63.8%→82.5%) are from specific dual-arm Franka tasks; broader coverage across embodiments (single-arm, humanoid, mobile manipulation) in the real-world RL fine-tuning experiments (as opposed to the offline ranking eval) is not evident from available summaries.
- Relies on the RynnBrain/Qwen3-VL backbone, so RynnValue's zero-shot generalization is partly inherited from a strong pretrained VLM — it's unclear how much of the "scaling" benefit is attributable to temporal-distance training specifically versus general VLM visual/language competence.
- As with other cost-to-go/potential-based reward approaches, temporal distance is directional but not necessarily monotonic in true task quality — a policy could game apparent "time to goal" reduction without genuinely improving task completion, and the paper's anti-shortcut measures address training-time shortcuts more than downstream reward-hacking risk during RL fine-tuning.

## Open Questions

- How sensitive is downstream RL fine-tuning performance to noise/inconsistency in the source video timestamps across heterogeneous datasets collected under different conditions (teleop pace, camera framerate, etc.)?
- Does the value-isolation attention mechanism fully eliminate shortcut exploitation, or do more adversarial evaluations reveal residual reliance on superficial temporal cues?
- How does RynnValue's dense reward compare against learned progress/preference-based reward models specifically in terms of reward-hacking susceptibility during online RL, rather than just offline ranking correlation?
- Would combining temporal-distance supervision with even a small amount of preference data close any remaining gap to preference-supervised methods on in-distribution tasks, or is temporal distance strictly sufficient?

## Significance

RynnValue is a strong data point for the thesis that scalable, label-free supervision signals (here, timestamps) can outperform expensive human-annotated preference/progress signals for training general-purpose value/reward foundation models, directly targeting reward-model scaling as the bottleneck for RL post-training of generalist robot policies.

## Links

- [Paper](https://arxiv.org/abs/2608.09853)
- [GitHub](https://github.com/alibaba-damo-academy/RynnValue)
