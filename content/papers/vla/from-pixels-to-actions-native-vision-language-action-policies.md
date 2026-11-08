---
title: "From Pixels to Actions: Towards Native Vision-Language-Action Policies (NEO-VLA)"
date: 2026-11-04
topic: VLA
tags: [vla, encoder-free, flow-matching, architecture, benchmark]
source: https://arxiv.org/abs/2611.06918
venue: "arXiv"
---

## Summary

NEO-VLA removes the separately pretrained vision encoder that almost every current VLA relies on. Instead, lightweight convolutional patch layers tokenize raw pixels directly into a 2B-parameter, 40-layer vision-language backbone, with a flow-matching action expert reading cached features from selected backbone depths. The paper argues — and tries to show empirically — that native, action-trained visual tokenization can outperform transplanted VLM encoders for manipulation.

## Key Contributions

- An encoder-free VLA architecture where pixel tokenization is learned end-to-end inside the VLA backbone rather than inherited from a frozen or lightly fine-tuned VLM vision tower.
- A layer-wise probing analysis showing action-relevant visual signal often peaks in earlier backbone layers than the final representation a standard VLM would hand off, motivating the encoder-free design.
- Reported LIBERO results of 90.9% average success with the backbone frozen (vs. 79.5% for a Qwen3-VL-backed baseline and 84.5% for Gemma-3), rising to 95.3% with full fine-tuning, plus evaluation on LIBERO-plus and RoboTwin 2.0.

## Strengths

- The frozen-backbone comparison is the most interesting result: if a from-scratch, action-native tokenizer beats a frozen general-purpose VLM encoder by ~10+ points under matched conditions, that's a real architectural finding, not just a scaling claim.
- Testing across three benchmarks (LIBERO, LIBERO-plus, RoboTwin 2.0) gives more confidence than a single-benchmark result would.

## Weaknesses

- All detailed figures in circulation come from secondary aggregator coverage (hyper.ai, news summaries) rather than a direct read of the arXiv PDF at time of writing; the exact training data, compute budget, and ablation protocol need verification against the primary source.
- Dropping a pretrained VLM encoder forfeits whatever general visual/world knowledge that encoder carries from internet-scale pretraining — the paper's own finding that "full fine-tuning reduces but does not erase the gap" to the VLM baselines suggests this tradeoff is real, not just a training-recipe artifact.
- LIBERO-family benchmarks are simulation-only and known to be sensitive to tokenization/action-head details that may not transfer to real-world manipulation diversity.

## Open Questions

- Does the encoder-free advantage hold at real-robot scale and under visual distribution shift, where pretrained VLM encoders are usually argued to help most?
- How does training cost (data + compute to train a 2B-parameter backbone from pixels for action) compare to fine-tuning an existing VLM backbone — is the frozen-backbone win actually cheaper to obtain in practice?

## Significance

If the frozen-backbone result replicates, it's a useful corrective to the default "take a VLM, bolt on an action head" recipe that dominates current VLA design, and complements this vault's existing "What Makes an Efficient VLA?" finding that action-head initialization from the language backbone matters more than decoder choice — here the claim is one level earlier, about where visual tokenization itself should live.

## Links

- [arXiv abstract](https://arxiv.org/abs/2611.06918)
- [hyper.ai summary](https://hyper.ai/en/papers/2611.06918)
