---
title: "GreenWAM: A World Foundation Model for Robotics"
date: 2026-10-13
topic: WorldModels
tags: [world-model, world-action-model, foundation-model, cross-embodiment, humanoid]
source: https://arxiv.org/abs/2610.18774
venue: "arXiv (Sber Robotics Center technical report)"
---

## Summary

GreenWAM is a world foundation model from Sber Robotics Center, built on NVIDIA's Cosmos 3 Edge and adapted to 20 different robot families through a shared joint-coordinate space. It is trained jointly in visual, action-conditioned, and world-action modes, and splits off a separate action expert for policy execution — positioning it as both a world model and a usable control policy across many embodiments at once.

## Key Contributions

- A shared joint-coordinate space that lets one world-action model span 20 distinct robot families, rather than being retrained per embodiment.
- A training recipe that mixes visual (pixel prediction), action-conditioned, and joint world-action objectives within a single model built on a Cosmos 3 Edge backbone.
- A distilled single-step variant reported to run at 28.3 Hz on real hardware, addressing the usual latency penalty of diffusion/video-based world models.

## Strengths

- Building on an existing strong video foundation model (Cosmos 3 Edge) rather than training a world model from scratch is a sensible way to inherit general visual dynamics knowledge before specializing to robotics.
- Reporting both world-model fidelity metrics (trajectory/depth/3D accuracy on WorldArena 1.0) and downstream policy results (RoboTwin 2.0, zero-shot LIBERO-Plus) gives a more complete picture than papers that report only one side.
- A real humanoid comparison against policies adapted from π0.5 and from the Cosmos 3 Edge backbone directly, rather than only simulation benchmarks, is a meaningful real-world check.

## Weaknesses

- As a technical report rather than a peer-reviewed paper, and one whose numbers are currently only available via secondary coverage, specific headline figures (e.g., LIBERO/WorldArena scores cited by third-party blogs) should be checked against the primary source once broadly accessible.
- Spanning 20 robot families via a shared coordinate space is an ambitious unification claim; how evenly performance holds across that full embodiment range (vs. being strongest on a handful of flagship platforms) isn't yet independently clear.

## Open Questions

- How does GreenWAM's shared-coordinate-space approach handle robot families with fundamentally different degrees of freedom (e.g., a parallel gripper arm vs. a 20+ DoF dexterous humanoid hand) without losing precision on either end?
- Does the 28.3 Hz distilled single-step variant retain most of the full model's world-model fidelity, or is there a meaningful accuracy/speed trade-off?

## Significance

A large-scale push toward a single world-action foundation model spanning dozens of robot embodiments at once (rather than the typical one-model-per-platform approach), and a direct real-humanoid comparison against π0.5 gives it a credible claim to state-of-the-art status on at least that comparison.

## Links

- [Paper](https://arxiv.org/abs/2610.18774)
