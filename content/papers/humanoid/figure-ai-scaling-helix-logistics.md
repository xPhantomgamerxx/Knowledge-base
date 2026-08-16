---
title: "Scaling Helix: A New State of the Art in Humanoid Logistics"
date: 2026-07-01
topic: Humanoid
tags: [humanoid, figure-ai, helix, deployment, logistics, industry]
source: https://www.figure.ai/news/scaling-helix-logistics
venue: "blog (Figure AI)"
---

## Summary

A Figure AI progress update on Helix (their humanoid VLA) applied to warehouse and logistics package handling. Reports per-package handling time down to ~4.05 seconds (~20% faster than a prior baseline), label-orientation-for-scanning accuracy up to ~95% from ~70%, and new robustness to deformable objects (poly bags, flat envelopes) rather than only rigid boxes — including learned auxiliary behaviors like patting down wrinkled mailers to improve barcode reads. Attributed to upgrades in "System 1," the low-level visuomotor control policy, including "implicit stereo vision" for depth-aware motion. This is the vault's first logged entry on Figure AI.

## Key Contributions

- Quantified throughput/accuracy gains on a real deployed logistics task.
- Extension of humanoid dexterous manipulation to deformable (non-rigid) objects.
- A stereo-depth perception upgrade to the low-level control policy.

## Strengths

- Real-world, large-scale deployed-task evidence (warehouse logistics) rather than a lab demo.
- Concrete before/after metrics for handling time and scan accuracy.

## Weaknesses

- No architectural or training detail is disclosed publicly (proprietary).
- Numbers are self-reported by Figure with no independent benchmark.
- Exact publish date could not be pinned down with confidence.

## Open Questions

- What specifically changed in "System 1" beyond "implicit stereo vision"?
- Is there any technical report accompanying this beyond the blog post?

## Significance

Figure AI's Helix line is one of the most closely watched humanoid VLA efforts in industry; this deployment update on deformable-object handling and throughput was a notable gap in this vault's prior coverage.

## Links

- [Blog](https://www.figure.ai/news/scaling-helix-logistics)
