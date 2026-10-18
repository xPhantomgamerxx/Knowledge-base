---
title: "LIBERO-RIG: A Hardware-Setup Robustness Benchmark for Vision-Language-Action Models"
date: 2026-10-13
topic: VLA
tags: [vla, benchmark, robustness, evaluation, hardware]
source: https://deeplearn.org/arxiv/847630/libero-rig:-a-hardware-setup-robustness-benchmark-for-vision-language-action-models
venue: "arXiv"
---

## Summary

LIBERO-RIG is a robustness benchmark that perturbs only the physical rig around a fixed LIBERO task set — camera mounting angle, calibration error, controller rate, gripper pad material — rather than the scene or sensing content that most robustness benchmarks (like LIBERO-Plus) vary. It covers 11 perturbation axes at 5 severity levels each (210 conditions total across the four LIBERO suites) and evaluates nine recent VLA models with 500 episodes per condition.

## Key Contributions

- Isolates "hardware setup" as its own robustness axis, distinct from scene/sensing perturbations, filling a gap between LIBERO-Plus-style content robustness and purely algorithmic evaluation.
- A large, systematic sweep (210 conditions × 9 models × 500 episodes) rather than a handful of spot-checked perturbations.
- Finds that pooled success drops from 0.932 at baseline to 0.767 at middle severity and 0.509 at the highest severity — a substantial, previously under-measured degradation.

## Strengths

- The finding that training on *visual* perturbations doesn't fix faults from hardware-setup changes that leave the camera image itself unchanged (e.g., controller rate, gripper pad) is a genuinely useful and non-obvious result — it shows visual-augmentation robustness training has a real blind spot.
- Releasing fixed perturbation-parameter manifests per episode makes the benchmark reproducible rather than only descriptive.

## Weaknesses

- Built entirely on LIBERO's simulated task suite; hardware-setup perturbations are inherently about physical reality, so the benchmark's simulated proxies for things like controller latency or gripper pad friction may not fully capture real deployment variance.
- Nine models is a reasonable but not exhaustive sample of the current VLA landscape, and the paper doesn't yet report whether any training-time fix closes the hardware-robustness gap it identifies.

## Open Questions

- Does any existing robustness technique (domain randomization over simulated controller rate/latency, robust gripper force/torque conditioning) actually close the gap this benchmark reveals, or is this an open problem?
- How well does performance degradation on LIBERO-RIG's simulated hardware perturbations correlate with real-robot hardware variation across physical setups?

## Significance

Complements LIBERO-Plus by covering a robustness axis (physical rig variation) that scene/sensing-focused benchmarks miss, and its headline finding — that visual-perturbation training doesn't transfer to hardware-setup robustness — is a useful caution against assuming one style of augmentation covers all deployment variance.

## Links

- [Paper (mirror)](https://deeplearn.org/arxiv/847630/libero-rig:-a-hardware-setup-robustness-benchmark-for-vision-language-action-models)
