---
title: "ZimaBlue: Evolving Generalizable World Action Models through Scalable Video Pre-training"
date: 2026-08-31
topic: WorldModels
tags: [world-action-model, video-pretraining, scaling]
source: https://arxiv.org/pdf/2609.00188
venue: "arXiv"
---

## Summary

ZimaBlue is a world-action model trained with a three-stage curriculum: causal embodied video pretraining on human and robot egocentric video, video-action mid-training on heterogeneous robot trajectories, and finally target-robot specialization. It pairs a high-capacity "Slow DiT" for dynamics modeling with a lightweight "Fast DiT" for 30Hz real-time action generation.

## Key Contributions

- A three-stage curriculum that separates broad visual-dynamics learning from robot-specific action grounding.
- A dual slow/fast DiT architecture decoupling world modeling from real-time control.
- A reported scaling result: increasing embodied video pretraining from 0 to 120k+ hours lifts zero-shot real-robot success from 36.1% to 77.8%.

## Strengths

- The direct ablation of pretraining video hours against zero-shot transfer is a genuinely useful scaling-law data point for the field.
- The fast branch's ability to run at 30Hz on a single RTX 4090 is a concrete, checkable efficiency claim.

## Weaknesses

- No verified public code or model release could be found at time of writing.
- All reported numbers come from secondary aggregator pages rather than the primary PDF, so methodology details (eval protocol, task selection) could not be independently confirmed.

## Open Questions

- Does the scaling curve on egocentric video hours saturate, or would even more data keep helping?
- How sensitive is the Fast DiT's 30Hz claim to action-chunk length and task complexity?

## Significance

Adds a concrete scaling-law data point (hours of egocentric video pretraining vs. zero-shot success) to the fast-growing world-action-model literature already dominant in this vault's World Models section.

## Links

- [Paper](https://arxiv.org/pdf/2609.00188)
