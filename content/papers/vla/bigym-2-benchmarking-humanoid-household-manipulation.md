---
title: "BiGym 2.0: Benchmarking Learned and Agent-Developed Policies for Humanoid Household Manipulation"
date: 2026-10-06
topic: VLA
tags: [vla, benchmark, humanoid, robotics]
source: https://arxiv.org/abs/2610.07594
venue: "arXiv"
---

## Summary

BiGym 2.0 extends the original BiGym mobile bi-manual manipulation benchmark to the Unitree G1 humanoid across 20 household tasks, supplying 60 VR-collected human demonstrations per task with multi-camera and full-body execution records, and benchmarks VLA fine-tuning, imitation learning, demo-driven RL, and LLM coding agents against each other under a unified whole-body controller.

## Key Contributions

- A humanoid-specific extension of BiGym with 20 household tasks and dense, VR-collected human demonstrations including full-body execution traces.
- A unified whole-body controller usable for both demonstration collection and policy evaluation, rather than simplifying locomotion with a separate controller.
- A four-way comparison across VLA fine-tuning, imitation learning, demo-driven RL, and LLM coding agents on the same task suite.
- Open-sourced environments, demonstrations, and evaluation traces (swirl-uk/BiGym2).

## Strengths

- Direct, apples-to-apples comparison of four very different policy paradigms (including coding agents) on the same humanoid benchmark is unusually broad and useful for the field.
- Finding that VLA fine-tuning gets the best nine-task mean, while agent-developed programs beat demo-driven RL baselines, is a genuinely informative result about where each paradigm currently stands.
- Full open-sourcing of environments, demos, and traces supports reproducibility and follow-up work.

## Weaknesses

- Reported open problems (cross-workspace stacking, low π0.5 performance on pick-box, difficulty of multi-object transport for IL/RL/agents) show the benchmark is still far from solved, limiting how much any single number should be trusted as "humanoid manipulation solved."
- The coding-agent baselines reportedly use GPT-6 Astra and Claude Opus 5.5 per some sources, which could not be independently verified in the available material.

## Open Questions

- Will the open problems identified (stacking, pick-box, multi-object transport) prove to be benchmark-specific quirks or genuine capability gaps across the field?
- How comparable is this benchmark's difficulty to other emerging humanoid household benchmarks (e.g., HumanoidArena, Labimus) for cross-benchmark generalization claims?

## Significance

A substantial new humanoid-specific benchmark that broadens evaluation beyond tabletop arm manipulation to whole-body household tasks, and one of the first to put VLA fine-tuning, imitation learning, RL, and LLM coding agents on genuinely equal footing for comparison.

## Links

- [Paper](https://arxiv.org/abs/2610.07594)
