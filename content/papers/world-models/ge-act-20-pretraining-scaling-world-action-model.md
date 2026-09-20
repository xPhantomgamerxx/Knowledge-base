---
title: "GE-Act 2.0: Pretraining and Scaling a World-Action Model for Robotic Manipulation"
date: 2026-09-04
topic: WorldModels
tags: [world-action-model, data-scaling, vla-posttraining, cross-embodiment, from-scratch-pretraining, agibot]
source: https://arxiv.org/abs/2609.05588
venue: "arXiv (AgiBot Research Team)"
---

## Summary

AgiBot's Genie Envisioner Act 2.0 trains all generative and action components of a world-action model from scratch on manipulation data (rather than inheriting a pretrained video-generation backbone), combining a control-oriented autoencoder, a single-step visual planner, and an inverse dynamics model. It is the first systematic test of scaling world-action-model training data two orders of magnitude (from ~300 to ~30,000 hours).

## Key Contributions

- Control-oriented autoencoder (CoAE) that compresses observations while retaining action/instruction-relevant information under aggressive compression
- Single-step visual planner (SVP) producing a full future state in one differentiable pass instead of iterative video generation
- Decoupled pretraining of visual planning and inverse dynamics on complementary data sources
- First controlled study of world-action-model scaling laws under two-orders-of-magnitude data growth, showing zero-shot out-of-distribution gains including for a sparsely-represented embodiment

## Strengths

- Directly tests the "does more data help" question for world-action models at a scale rarely reported (300h → 30,000h), providing rare empirical scaling evidence in this subfield
- From-scratch initialization (rather than repurposing a video generator) isolates the world-action-model-specific pretraining signal from generic video-generation priors
- Generalization to an underrepresented embodiment is a meaningful robustness signal

## Weaknesses

- As with most industrial-scale scaling papers, exact data composition/curation details are likely underspecified for external reproduction
- Comparison against video-generator-initialized baselines (the dominant paradigm) could be more rigorously controlled for compute parity
- Without internet-video pretraining, the model likely sacrifices some of the broad visual/physical priors that give video-pretrained WAMs their generalization edge; head-to-head OOD comparison is the key missing piece

## Open Questions

- Where does the scaling curve saturate, and is 30,000 hours near a plateau or still on a steep part of the curve?
- How much of the gain comes from data volume vs. data diversity (embodiments/tasks/environments)?
- Does from-scratch WAM pretraining scale as favorably with data/compute as video-pretrained WAMs, or hit a lower generalization ceiling?

## Significance

A direct, large-scale empirical data point for scaling real/sim data pipelines for world-action models — a rare case of an industrial lab publishing a controlled scaling study rather than just a capability announcement, and a direct test of whether internet-video pretraining is actually necessary for WAMs.

## Links

- [Paper](https://arxiv.org/abs/2609.05588)
