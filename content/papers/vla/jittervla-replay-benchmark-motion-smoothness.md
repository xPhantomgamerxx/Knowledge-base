---
title: "JitterVLA: A Replay Benchmark for Motion Smoothness in VLA-Driven Human-Robot Manipulation"
date: 2026-10-13
topic: VLA
tags: [vla, benchmark, motion-quality, evaluation, human-robot-interaction]
source: https://arxiv.org/abs/2610.13628
venue: "arXiv"
---

## Summary

JitterVLA is a benchmark targeting a metric most VLA evaluations ignore: motion smoothness of the executed trajectory, specifically in human-robot manipulation settings where jerky or jittery motion affects perceived safety and collaboration quality, not just task success rate.

## Key Contributions

- Introduces a replay-based evaluation protocol for quantifying motion smoothness/jitter of VLA-driven manipulation, separate from the standard binary task-success metric.
- Targets the human-robot interaction context specifically, where motion quality (not just whether the task completes) materially affects how safe or acceptable a robot's behavior feels to a human collaborator.

## Strengths

- Success-rate-only evaluation is a known blind spot in the VLA literature (echoed by other recent work like "Is Success All You Need?"), and this benchmark gives a concrete, reusable way to measure a specific, underexamined failure mode.
- A replay-based protocol (rather than requiring live human-robot trials for every evaluated policy) makes the benchmark more practical to apply broadly across models.

## Weaknesses

- Motion-smoothness metrics computed from replay may not fully capture the subjective human perception of jerkiness that motivates the benchmark in the first place — some validation against actual human ratings would strengthen the case.
- As a benchmark paper, it doesn't itself propose a fix for jittery VLA output; its value depends on the field adopting it and acting on the gaps it reveals.

## Open Questions

- Does the benchmark reveal a consistent "smoothness vs. success rate" trade-off across existing VLAs, or are some policies strong on both axes simultaneously?
- How well do standard action-chunking or low-pass filtering post-processing tricks close the gaps the benchmark reveals, versus requiring architectural changes?

## Significance

A useful complement to the growing body of VLA robustness/behavioral-quality benchmarks (LIBERO-Plus, LIBERO-RIG, this week's AXIS-Bench) — pushing evaluation beyond raw success rate toward the execution-quality dimensions that matter for real deployment alongside humans.

## Links

- [Paper](https://arxiv.org/abs/2610.13628)
