---
title: "HumanTracker: Towards Comprehensive and Human-Aligned Motion Tracking Benchmark"
date: 2026-08-13
topic: Humanoid
tags: [humanoid, benchmark, motion-tracking, evaluation-metrics]
source: https://arxiv.org/abs/2608.13555
venue: "arXiv"
---

## Summary

HumanTracker introduces a ~153-hour optical motion-capture benchmark spanning four motion families (daily tasks, highly dynamic motions, interaction, ground-level), with text labels, plus "HumanScore," a preference-aligned metric trained on 12K motion pairs (24K motions) designed to catch physical artifacts — foot skating, mistimed contacts — that standard kinematic-error metrics miss.

## Key Contributions

- A large (~153-hour) and motion-diverse benchmark spanning categories that most existing humanoid motion-tracking benchmarks don't jointly cover, particularly ground-level and highly dynamic motions alongside more common daily-task motions.
- HumanScore, a learned preference-aligned metric, directly addresses a known weakness of standard kinematic-error metrics (e.g. joint-angle MSE), which can score a motion as accurate while missing perceptually and physically obvious artifacts like foot skating.
- Training the metric on human preference pairs (12K pairs, 24K motions) grounds "quality" in what evaluators actually perceive as good motion, rather than a purely geometric definition.

## Strengths

- Standard kinematic-error metrics genuinely do miss the artifacts HumanScore targets — this is a well-known and legitimate gap in motion-tracking evaluation, and a dedicated preference-aligned metric is a sensible response.
- Breadth across four motion families, including ground-level motion (often excluded from benchmarks focused on standing/walking humanoids), is a meaningful step toward more comprehensive evaluation.

## Weaknesses

- A learned preference metric is only as good as the diversity and consistency of its training preference pairs; 12K pairs is a moderate scale that may not cover the full space of motion artifacts across all four motion families evenly.
- As a benchmark and metric contribution rather than a new tracking method, HumanTracker's value is entirely dependent on community adoption — its usefulness will only be evident once other tracking-policy papers report results against it.

## Open Questions

- Does HumanScore's preference-based judgment correlate well with actual physical plausibility (e.g. as verified against real hardware execution), or could it encode spurious visual preferences that don't map to real-world tracking quality?
- Will HumanTracker be adopted broadly enough across future humanoid whole-body tracking papers to serve its intended role as a standard comparison point?

## Significance

A benchmark/evaluation contribution addressing the genuine gap between standard kinematic-error metrics and perceived/physical motion quality — relevant to the broader cluster of humanoid whole-body tracking and teleoperation benchmarks already logged in this vault (ThorArena, HumanoidArena).

## Links

- [Paper](https://arxiv.org/abs/2608.13555)
