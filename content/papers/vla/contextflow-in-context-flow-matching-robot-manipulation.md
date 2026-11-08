---
title: "ContextFlow: In-Context Flow Matching for Robot Manipulation"
date: 2026-09-08
topic: VLA
tags: [vla, in-context-learning, flow-matching, few-shot, vla-posttraining]
source: https://arxiv.org/abs/2609.06852
venue: "ECCV 2026"
---

## Summary

ContextFlow brings in-context imitation learning into a flow-matching policy instead of the autoregressive, discretized-action setups most prior in-context robot learning (e.g. ICRT) used. A perceiver-style context compressor encodes a handful of demonstrations into compact latents that condition continuous flow-matching action generation, aiming to avoid the compounding discretization error that hurts autoregressive in-context methods on unseen task configurations.

## Key Contributions

- Conditional flow-matching formulation for in-context imitation learning, conditioning action generation on compressed demonstration latents rather than fine-tuned weights.
- Perceiver-style compression of visual, proprioceptive, and action-sequence demonstration data into a fixed-size context representation.
- Reports beating ICRT by 35 percentage points average success on unseen LIBERO task configurations, and roughly matching fine-tuned π0 on unseen tasks without any fine-tuning; real-robot results include 40% success on an unseen pen-uncapping configuration on single-arm and bimanual setups.

## Strengths

- Matching a fine-tuned π0 on unseen tasks with zero fine-tuning, if it holds up, is a strong practical result for deployment scenarios where per-task fine-tuning is impractical.
- Using a continuous generative action head for in-context learning is a sensible response to a known failure mode (discretization-induced compounding error) in prior autoregressive in-context approaches, and the LIBERO comparison against ICRT directly targets that failure mode.

## Weaknesses

- The "roughly matches fine-tuned π0" claim is on unseen tasks specifically; it's unclear from available coverage how it compares to fine-tuned baselines on in-distribution tasks, where fine-tuning might still win by a larger margin.
- Real-world evaluation (40% on one new task configuration) is thin evidence — a single real-world success-rate number on one task doesn't establish robustness the way the LIBERO numbers might suggest.
- Author-reported dataset details (1,318 real ALOHA trajectories across 25 configurations) come from secondary coverage, not a verified primary-source read.

## Open Questions

- How does context length (number and diversity of demonstrations) trade off against inference latency and performance — is there a point of diminishing or negative returns as in other in-context robot learning work?
- Does the perceiver-style compression lose task-relevant fine detail for contact-rich or precision tasks compared to the richer, if slower, raw-demonstration conditioning some competitors use?

## Significance

This is another entry in the growing cluster of in-context/few-shot VLA adaptation work already represented in this vault (StellaVLA, SynthICL, ICI-VLA, Retrieval-VLA), and specifically targets the gap between discrete-action in-context methods and generative action heads — a distinction that matters as flow-matching/diffusion action experts become the default for high-performing VLAs.

## Links

- [arXiv abstract](https://arxiv.org/abs/2609.06852)
- [Project page](https://dingjiansw101.github.io/contextflow-page/)
