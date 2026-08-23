---
title: "Reflex: Enabling Fast and Predictive Vision-Language-Action Models for Reaction-Critical Manipulation"
date: 2026-08-16
topic: VLA
tags: [vla, latency, benchmark, temporal-reasoning, reaction-critical-manipulation]
source: https://arxiv.org/abs/2608.14379
venue: "arXiv"
---

## Summary

This paper introduces ReflexBench, a benchmark for dynamic, reaction-critical manipulation tasks with configurable inference latency under synchronous and asynchronous execution, and ReflexVLA, an efficient VLA designed to perform well on it without large-scale robot-data pretraining. ReflexVLA improves temporal reasoning via latent future prediction and multi-frame temporal fusion, and reduces deployment latency through batched visual encoding and CUDA Graph replay.

## Key Contributions

- ReflexBench: six dynamic manipulation tasks with a latency-aware evaluation harness that decouples simulator stepping from robot control, exposing how policies degrade under realistic inference delay rather than assuming zero-latency execution.
- ReflexVLA: latent future prediction and multi-frame temporal fusion added to the vision backbone specifically to improve reaction to fast-changing scenes.
- System-level latency optimizations (batched visual encoding, CUDA Graph replay) that cut deployment latency to 65.0ms while reporting a 50.4% average success rate on the latency-aware benchmark.

## Strengths

- Explicitly modeling and benchmarking inference latency as a first-class variable is a genuinely underexplored angle — most VLA benchmarks report success rate without accounting for how real deployment latency changes outcomes on dynamic tasks.
- Achieving competitive results without large-scale robot-data pretraining suggests the latency/temporal-reasoning improvements are doing real work rather than being masked by data scale.

## Weaknesses

- A 50.4% average success rate, while a meaningful benchmark contribution, indicates reaction-critical manipulation remains far from solved — the paper should be read as establishing a hard benchmark rather than reporting a strong absolute result.
- CUDA Graph replay and batched encoding are hardware/framework-specific optimizations; portability to other inference stacks or edge hardware is unclear.

## Open Questions

- How does ReflexVLA's performance scale if combined with the larger-scale pretraining it explicitly avoids — is the latency/temporal-reasoning contribution complementary or a substitute for data scale?
- Does the six-task benchmark generalize as a proxy for reaction-critical manipulation broadly, or does it capture idiosyncrasies of the specific dynamic tasks chosen?

## Significance

A notable, differently-scoped paper from the earlier "Reflex: Real-Time VLA Control through Streaming Inference" already logged in this vault — this one contributes both a new latency-aware benchmark (ReflexBench) and a policy architecture (ReflexVLA) targeting the same broad problem (fast, reaction-critical control) from a different technical angle.

## Links

- [Paper](https://arxiv.org/abs/2608.14379)
- [GitHub](https://github.com/ReflexVLA/reflexvla.github.io)
