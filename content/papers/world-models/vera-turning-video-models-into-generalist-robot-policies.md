---
title: "Turning Video Models into Generalist Robot Policies (VERA)"
date: 2026-05-28
topic: WorldModels
tags: [world-models, video-prediction, inverse-dynamics, cross-embodiment, dexterous-manipulation]
source: https://arxiv.org/abs/2605.27817
venue: "arXiv"
---

## Summary

Rather than fine-tuning a video generative model end-to-end for control, VERA keeps the video "planner" embodiment-agnostic and unmodified, and trains a separate, embodiment-specific inverse dynamics model (IDM) to translate predicted video into executable actions. This decoupling lets different video planners be swapped without retraining the IDM, and lets the IDM be trained independently on cheap self-play data. Evaluated on zero-shot Panda-arm manipulation and 16-DoF Allegro-hand dexterous cube reorientation.

## Key Contributions

- A decoupled "any video planner + embodiment-specific IDM" architecture.
- An IDM trainable from self-play without paired video-action data from the target robot.
- Demonstrated zero-shot cross-embodiment transfer, including a high-DoF dexterous-hand task.

## Strengths

- The modular/swappable design is practically appealing — video model progress can be adopted without re-deriving action heads.
- Dexterous-hand results are a harder generalization test than typical pick-and-place benchmarks.

## Weaknesses

- Performance is bottlenecked by the quality of the underlying video planner.
- The IDM's generalization to truly novel embodiments beyond those tested is unproven.

## Open Questions

- How well does the IDM generalize to embodiments not seen during self-play data collection?
- Is the full video-generation-plus-IDM pipeline feasible at real-time control rates?

## Significance

A clean architectural decoupling of "what to do" (video prediction) from "how to actuate it" (inverse dynamics) that could let world-model progress and embodiment-specific control progress evolve independently.

## Links

- [Paper](https://arxiv.org/abs/2605.27817)
