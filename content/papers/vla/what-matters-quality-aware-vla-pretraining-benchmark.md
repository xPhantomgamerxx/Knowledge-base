---
title: "What Matters in Quality-Aware VLA Pretraining: A Benchmark and Empirical Study"
date: 2026-10-13
topic: VLA
tags: [vla, pretraining, data-quality, benchmark, data-augmentation, vla-posttraining]
source: https://deeplearn.org/arxiv/847613/what-matters-in-quality-aware-vla-pretraining:-a-benchmark-and-empirical-study
venue: "arXiv"
---

## Summary

A systematic empirical study of how demonstration quality should be used during VLA pretraining — comparing weighting, filtering, and conditioning strategies across different reward definitions and label granularities — introduced alongside a new benchmark, AXIS-Bench, built from crowdsourced simulation demonstrations with recorded object/contact states so quality labels can be recomputed consistently.

## Key Contributions

- A controlled comparison of three families of quality-aware pretraining strategies (weighting, filtering, conditioning) across multiple reward definitions and label granularities, holding demonstration count and training budget fixed per VLA.
- AXIS-Bench: a benchmark with replayable trajectories, recorded contact/object state, and support for user-defined real-world tasks, specifically designed so quality metrics can be recomputed on shared trajectories rather than frozen at collection time.
- A real-world transfer result: simulation pretraining with the paper's quality-aware recipe raised real-world task success from 9.6% to 31.7%.

## Strengths

- Deliberately uses naturally suboptimal (not synthetically corrupted) human demonstrations, which makes the quality-filtering/weighting comparison more representative of real crowdsourced data collection than typical synthetic-noise ablations.
- The finding that approach-aware episode conditioning beats plain behavior cloning across three different VLAs is a reasonably robust signal, since it holds across architectures rather than being specific to one model.
- A 9.6%→31.7% real-world jump from simulation pretraining is a substantial, concrete number that grounds the otherwise abstract "data quality" discussion in a deployment-relevant outcome.

## Weaknesses

- The paper reports that conditioning and filtering each favor a different label granularity on average, with some model-dependent reversals — this means there isn't yet a single clear recipe, just an empirical map of what tends to work where.
- 5,000 demonstrations and 24 target tasks, while a reasonable scale for a controlled study, is still modest relative to the pretraining corpora used by frontier VLA foundation models; it's unclear how findings hold at that larger scale.

## Open Questions

- Does the "constant quality tag at fine-tuning time helps after conditioned pretraining" finding generalize to settings where the fine-tuning task distribution is very different from the pretraining task distribution?
- How sensitive are the conclusions to the specific reward/quality definitions chosen, versus being genuinely architecture- and task-agnostic principles?

## Significance

Directly on-point for the cross-cutting data-and-post-training priority: it's an empirical study of exactly how to make the most of imperfect demonstration data during VLA pretraining, with a reusable benchmark (AXIS-Bench) for others to build on.

## Links

- [Paper (mirror)](https://deeplearn.org/arxiv/847613/what-matters-in-quality-aware-vla-pretraining:-a-benchmark-and-empirical-study)
- [Project page](https://axis-bench.github.io/)
