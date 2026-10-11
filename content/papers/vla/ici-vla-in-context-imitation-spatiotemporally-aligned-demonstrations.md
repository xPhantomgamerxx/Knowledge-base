---
title: "ICI-VLA: In-Context Imitation with Spatiotemporally Aligned Demonstrations for Vision-Language-Action Models"
date: 2026-09-07
topic: VLA
tags: [vla, in-context-learning, imitation-learning, vla-posttraining]
source: https://arxiv.org/abs/2609.07581
venue: "arXiv / IEEE CDC 2026"
---

## Summary

ICI-VLA lets a frozen text-action VLA policy adapt to new tasks at test time by conditioning on retrieved demonstrations from a pre-built library rather than updating any weights, using spatiotemporal alignment and masking to make the retrieved context usable. It reports 97.7% average success on LIBERO, 60.4% on RoboTwin 2.0, and 83.2% across four real-world tasks, beating OpenVLA-OFT and a naive in-context-learning ablation.

## Key Contributions

- Spatiotemporally aligned retrieval of demonstrations for in-context conditioning of frozen VLA policies.
- A masking scheme that removes the sharp degradation seen in naive in-context learning without masking.
- Evaluation across LIBERO, LIBERO-Long, RoboTwin 2.0, and four physical tasks.

## Strengths

- No gradient updates needed at deployment, so a single frozen policy can specialize per task on the fly.
- Large reported margin over a naive in-context-learning ablation, showing the alignment/masking design matters, not just the presence of context.
- Tests span both simulation and real robots.

## Weaknesses

- Comparison against OpenVLA-OFT is at benchmark level rather than a fully controlled head-to-head.
- Depends on a pre-built demonstration library, so coverage and retrieval quality bound performance on tasks far from the library.
- The short paper format leaves limited room for failure-mode analysis of retrieval errors.

## Open Questions

- How does performance degrade as the demonstration library shrinks or becomes noisier/mismatched?
- Can retrieval latency be kept low enough for closed-loop control at higher frequencies?

## Significance

Adds to a fast-growing line of training-free/in-context adaptation methods (alongside RA-VLA, StellaVLA) that let a single deployed VLA specialize to new tasks without costly re-training, which matters for real-world fleets that can't retrain per task.

## Links

- [Paper](https://arxiv.org/abs/2609.07581)
