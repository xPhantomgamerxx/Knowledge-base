---
title: "SIMPLE: Simulation-Based Policy Learning and Evaluation for Humanoid Loco-Manipulation"
date: 2026-06-12
topic: Humanoid
tags: [humanoid, benchmark, simulation, loco-manipulation, whole-body-control]
source: https://arxiv.org/abs/2606.08278
venue: "arXiv"
---

## Summary

A unified humanoid loco-manipulation simulation testbed combining MuJoCo (for contact-rich dynamics accuracy) with IsaacSim (for photorealistic rendering), covering 60 diverse whole-body tasks across 50 indoor scenes with 1,000+ object assets — positioned as filling a gap where prior benchmarks mostly cover tabletop or wheeled-robot manipulation rather than reproducible whole-body humanoid loco-manipulation.

## Key Contributions

- A dual-engine simulation stack combining contact-dynamics accuracy with photorealistic rendering.
- Large task/scene/asset diversity (60 tasks, 50 scenes, 1,000+ assets) for whole-body humanoid benchmarking.

## Strengths

- Addresses a recognized reproducibility gap in humanoid loco-manipulation evaluation.
- Substantially larger scale than narrower prior benchmarks.

## Weaknesses

- Baseline policy results, evaluation protocol, and sim-to-real correlation claims could not be confirmed from available sources.

## Open Questions

- What policies/baselines are reported on this benchmark?
- Is there any real-robot validation of the benchmark's predictive value?

## Significance

A large-scale, dual-engine simulation benchmark aimed at making whole-body humanoid loco-manipulation research more standardized and reproducible.

## Links

- [Paper](https://arxiv.org/abs/2606.08278)
