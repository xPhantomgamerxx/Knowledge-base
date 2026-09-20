---
title: "ForesightSafety-VLA: A Unified Diagnostic Safety Benchmark for Vision-Language-Action Models"
date: 2026-06-25
topic: VLA
tags: [safety, benchmark, diagnostic-evaluation]
source: https://arxiv.org/abs/2606.27079
venue: "arXiv"
---

## Summary

A diagnostic safety benchmark making safety itself (not just task success) the primary evaluation target for VLA systems, defining a 13-category safety taxonomy (physical interaction "Safe-Core," instruction-side "Safe-Lang," perception-side "Safe-Vis") and evaluating policies under controlled variation in scene structure, language command, and visual observation, with process-level metrics beyond binary success.

## Key Contributions

- 13-category safety taxonomy spanning physical, linguistic, and visual/perceptual safety dimensions, rather than a single monolithic "safe/unsafe" label
- New process-level metrics — cumulative safety cost (CC) and risk exposure time (RET) — that capture how risky a rollout was, not just whether it ended safely
- A four-quadrant decomposition crossing safe/unsafe with success/failure, letting researchers distinguish "safely failed," "unsafely succeeded," etc.

## Strengths

- Moving beyond binary safe/unsafe outcomes to process-level, time-integrated risk metrics (CC, RET) is a meaningful methodological improvement for safety evaluation
- Controlled, independent variation across scene/language/vision axes allows isolating which input modality drives unsafe behavior — useful diagnostic granularity

## Weaknesses

- As with most new benchmarks, adoption is uncertain, and a similarly-timed competing benchmark (LIBERO-Safety) risks fragmenting the safety-evaluation landscape rather than converging on one standard
- A 13-category taxonomy, while thorough, adds significant annotation/evaluation complexity that may limit how widely this benchmark gets adopted outside the authors' own follow-up work

## Open Questions

- How well do the CC/RET metrics correlate with real-world injury/damage risk, versus being an internally consistent but unvalidated proxy?
- Will the community converge on this taxonomy versus the competing LIBERO-Safety benchmark released around the same time?

## Significance

Part of a nascent but important wave of safety-specific VLA benchmarks emerging as VLA policies move toward real-world, human-proximate deployment — a category not previously well represented in this vault's tracked literature.

## Links

- [Paper](https://arxiv.org/abs/2606.27079)
