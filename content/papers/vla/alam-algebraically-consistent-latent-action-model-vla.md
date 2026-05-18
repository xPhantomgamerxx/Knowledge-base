---
title: "ALAM: Algebraically Consistent Latent Action Model for Vision-Language-Action Models"
date: 2026-05-13
topic: VLA
tags: [latent-action, flow-matching, pretraining, MetaWorld, LIBERO]
source: https://arxiv.org/abs/2605.10819
venue: "arXiv 2605.10819"
---

## Summary

ALAM learns algebraically structured latent transitions from action-free video by enforcing composition and reversal consistency on frame triplets, then uses the frozen pretrained encoder's latent transitions as auxiliary generative targets co-generated with robot actions under a joint flow-matching objective. This couples structured latent transitions with flow-based policy generation, bridging large-scale unlabeled video pretraining with downstream VLA fine-tuning.

## Key Contributions

- Algebraic regularization (composition + reversal consistency) reduces additivity and reversibility errors by 25–85× over unstructured latent-action baselines
- Raises average success on MetaWorld MT50 from 47.9% → 85.0% and LIBERO from 94.1% → 98.1%
- Joint flow-matching objective couples latent world-model supervision with action prediction at no extra inference cost

## Significance

ALAM demonstrates that imposing algebraic structure on latent action representations—rather than treating them as free embeddings—yields dramatic gains on both short- and long-horizon manipulation benchmarks, establishing a principled bridge between video pretraining and robot policy learning.

## Links

- [Paper](https://arxiv.org/abs/2605.10819)
