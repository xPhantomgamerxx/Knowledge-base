---
title: "ESP: Energy-Score Policy for One-Step Multimodal Action Generation"
date: 2026-10-06
topic: VLA
tags: [vla, action-generation, efficient-vla, robotics]
source: https://arxiv.org/abs/2610.07696
venue: "arXiv"
---

## Summary

ESP generates robot actions in a single forward pass rather than through iterative diffusion/flow-matching sampling, by training the action head with an energy-score objective (a strictly proper scoring rule capable of representing multimodal distributions) instead of mean-squared error. On LIBERO it reports task success comparable to a flow-matching baseline while cutting action-expert latency from 28.39 ms to 3.35 ms.

## Key Contributions

- Use of the energy score as a training objective for one-step, non-iterative multimodal action generation.
- Roughly an 8.5x latency reduction (28.39 ms to 3.35 ms) for the action-generation step relative to a flow-matching baseline, at comparable task success.
- Demonstration that a single-pass action head can still capture multimodal action distributions, a key motivation for why diffusion/flow approaches were adopted in the first place.

## Strengths

- Large, concrete latency win (roughly 8x) is directly useful for closed-loop control frequency, one of the main practical costs of diffusion/flow-based VLA action heads.
- Keeping success rate comparable to the flow-matching baseline, rather than trading accuracy for speed, is the ideal outcome for this kind of efficiency work, if the claim holds up broadly.

## Weaknesses

- Evaluated on LIBERO only in the available material; real-world validation isn't mentioned.
- Energy-score-based one-step generation is architecturally and theoretically distinct from the now-standard diffusion/flow-matching approach, so adoption may require retraining existing pipelines rather than a drop-in swap.

## Open Questions

- Does the energy-score objective hold up on tasks requiring finer multimodal distinctions (e.g., several very different but equally valid grasp strategies) than LIBERO's task suite may test?
- How does ESP compare to other one-step approaches (e.g., IMLE-VLA, One-Step Diffusion Policy) on the same benchmarks under matched conditions?

## Significance

One of several 2026 efforts (along with IMLE-VLA, One-Step Diffusion Policy) chasing single-pass, low-latency alternatives to iterative diffusion/flow action generation — important because action-head sampling latency is a direct bottleneck for high-frequency robot control.

## Links

- [Paper](https://arxiv.org/abs/2610.07696)
