---
title: "CrossTracer: Hierarchical Cross-Embodiment Navigation via Pixel-Space Trace Proposal and Embodiment-Conditioned Correction"
date: 2026-08-08
topic: VLA
tags: [vla, cross-embodiment, navigation, benchmark]
source: https://arxiv.org/abs/2608.06688
venue: "arXiv"
---

## Summary

CrossTracer addresses cross-embodiment navigation: a semantically plausible path for one robot may be physically infeasible for another. It represents navigation plans as normalized image-plane waypoints — a pixel-space interface bridging semantic reasoning and physical grounding — produced by a Vision-Language Trace Proposer (an adapted pretrained VLA) and refined by a CE-Adapter that predicts embodiment-conditioned residual corrections using robot embeddings, FiLM layers, and trace-to-visual cross-attention.

## Key Contributions

- A pixel-space waypoint representation used as a general-purpose cross-embodiment interface for navigation.
- A residual-correction adapter conditioned on embodiment identity, separating semantic path proposal from physical feasibility.
- On the NaviTrace benchmark, scores 45.68 total, beating Gemini-2.5-Pro by 10.01 points (28.1% relative improvement).

## Strengths

- Clean separation of semantic reasoning (handled by the VLA) from embodiment-specific physical grounding (handled by the adapter).
- Concrete, favorable benchmark comparison against a strong general-purpose VLM baseline.

## Weaknesses

- Scope is limited to navigation, not manipulation.
- Performance is bounded by the pretrained VLA backbone's quality.
- Benchmarked mainly against general VLMs rather than specialized navigation baselines.

## Open Questions

- How well does CrossTracer perform in real-world deployment beyond the NaviTrace benchmark?
- Does the CE-Adapter generalize to embodiments entirely unseen during training?
- What is the added compute/latency cost of the two-stage propose-then-correct pipeline?

## Significance

Extends the cross-embodiment generalization problem — well studied for manipulation in this vault — into navigation, with a concrete pixel-space representation that could be reused elsewhere.

## Links

- [Paper](https://arxiv.org/abs/2608.06688)
