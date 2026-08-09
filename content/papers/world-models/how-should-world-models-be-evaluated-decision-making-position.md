---
title: "How Should World Models Be Evaluated for Embodied Decision-Making? A Decision-Making-Centric Position"
date: 2026-06-28
topic: WorldModels
tags: [world-models, evaluation, position-paper]
source: https://arxiv.org/abs/2606.15032
venue: "arXiv"
---

## Summary

A position paper arguing that "world model" has come to cover many incompatible objects — action-conditioned simulators, latent imagination models, video predictors, synthetic-data engines — that are currently evaluated with mismatched, often visual-realism-centric metrics. It proposes that the decisive test should instead be whether a model supports reliable interventional (counterfactual) reasoning for decision-making.

## Key Contributions

- A taxonomy distinguishing the different objects currently labeled "world model" in the robotics/embodied-AI literature, highlighting that they serve different purposes and shouldn't share a single evaluation standard.
- An argument for interventional/counterfactual reasoning fidelity, rather than visual quality (e.g., FVD, perceptual similarity), as the primary evaluation axis for world models intended to support decision-making.
- A framing that directly challenges the current practice — visible across the many "WAM" and video-generation-derived world-model papers already in this vault — of implicitly treating video-generation quality as a proxy for control usefulness.

## Strengths

- This is a genuinely useful corrective given how saturated the "World Action Model" literature has become this quarter (dozens of near-identical papers), many of which lean heavily on visual-generation benchmarks that don't necessarily correlate with downstream control performance.
- Proposing interventional/counterfactual reasoning as the yardstick aligns with a well-established causal-inference framework, giving the proposal theoretical grounding rather than being an ad-hoc metric suggestion.

## Weaknesses

- As a position paper, it doesn't provide a concrete, adoptable benchmark or metric implementation — the field still needs someone to operationalize "interventional reasoning fidelity" into something researchers can actually report and compare against.
- Position papers proposing new evaluation paradigms often struggle for adoption against existing, easier-to-compute metrics (FVD, pixel MSE) unless accompanied by a ready-to-use benchmark suite, which this paper does not appear to supply.

## Open Questions

- Will a companion benchmark operationalizing this evaluation philosophy follow, and will the community adopt it over existing visual-quality metrics?
- How would the many existing "WAM" papers in this vault fare if re-evaluated under an interventional-reasoning-centric standard rather than their reported video-generation/task-success metrics?
- Is interventional reasoning fidelity itself measurable without ground-truth counterfactual outcomes, which are rarely available in real-world robot data?

## Significance

An important, timely critique of measurement practice in a subfield (world/world-action models) that this vault has tracked extensively; worth reading alongside the dozens of WAM papers already logged as a check on what their reported metrics actually demonstrate.

## Links

- [Paper](https://arxiv.org/abs/2606.15032)
