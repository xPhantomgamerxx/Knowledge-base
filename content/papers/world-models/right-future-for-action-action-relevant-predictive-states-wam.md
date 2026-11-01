---
title: "The Right Future for Action: Learning Action-Relevant Predictive States in World Action Models"
date: 2026-09-27
topic: WorldModels
tags: [world-action-model, representation-learning, ablation-study]
source: https://arxiv.org/pdf/2609.23369
venue: "arXiv"
---

## Summary

This paper asks a more foundational version of the question raised by DreamWAM and ForeWAM: what should a world-action model's predictive state actually preserve for the action expert, given that video-prediction objectives reward broad appearance/geometry/semantics while control may only need a narrow slice of that. It introduces "Action-Relevant Predictive States" (ARPS) and runs a systematic teacher ablation (V-JEPA2 vs. DINOv2 vs. VGGT vs. none) to isolate which future-representation choice actually transfers to control.

## Key Contributions

- A systematic ablation of different "future-state teacher" choices (V-JEPA2, DINOv2, VGGT, none) under one controlled world-action-model framework.
- A V-JEPA2-teacher ARPS variant reaching 99.2% average on LIBERO (99.0/100.0/98.6/99.0 across the Spatial/Object/Goal/Long suites).
- A no-teacher ablation showing performance drops specifically on long-horizon tasks (82.4 vs. 99.0 for Long), isolating where future-state supervision actually helps.
- A LIBERO-Plus robustness ablation showing removing the video loss costs 22.7 points (87.3→64.6), indicating video supervision matters specifically for OOD robustness, not just in-distribution accuracy.

## Strengths

- A genuinely controlled comparison across teacher choices, rather than a single new architecture benchmarked against unmatched baselines — more scientifically useful than most world-action-model papers in this space.
- The Long-suite-specific degradation under the no-teacher ablation is a believable, mechanistically interpretable result.

## Weaknesses

- The VGGT-teacher ablation underperforms even the no-teacher baseline on the Long suite (70.4 vs. 82.4), an unexplained result in available summaries — not all "richer" representations help, and the paper's own account of why some teachers hurt isn't resolved in what's searchable.
- Evaluation is LIBERO/LIBERO-Plus only; no real-robot validation was found in search results.

## Open Questions

- Why does a geometry-focused teacher (VGGT) actively hurt relative to no teacher at all, when DreamWAM's geometry branch (Depth Anything) reportedly helps?
- Does ARPS's teacher-selection story generalize to real-robot deployment, or is it a LIBERO-specific artifact?

## Significance

The most rigorous of this quarter's cluster of "what should a world-action model actually predict" papers (alongside DreamWAM and ForeWAM) — its controlled teacher ablation is a useful empirical anchor the field currently lacks.

## Links

- [Paper](https://arxiv.org/pdf/2609.23369)
