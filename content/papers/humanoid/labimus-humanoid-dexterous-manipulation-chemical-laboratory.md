---
title: "Labimus: A Simulation and Benchmark for Humanoid Dexterous Manipulation in Chemical Laboratory"
date: 2026-06-20
topic: Humanoid
tags: [humanoid, benchmark, simulation, dexterous-manipulation, scientific-automation]
source: https://arxiv.org/abs/2606.31037
venue: "arXiv"
---

## Summary

The first benchmark targeting humanoid dexterous manipulation specifically in organic-chemistry lab settings. It reconstructs 30+ functionally faithful lab-instrument assets via real-to-sim modeling of an actual chemistry workstation, and models a "Tianyi 2.0" humanoid performing precision-critical operations (e.g. solid-solid powder transfer) with articulated instruments, particle-based powder physics, and closed-loop instrument state readouts.

## Key Contributions

- The first simulation benchmark of its kind for lab-science humanoid manipulation.
- A real-to-sim asset library of 30+ chemistry-lab instruments.
- Particle-based powder physics combined with instrument-readout coupling for closed-loop task verification.

## Strengths

- A novel, under-served application domain (scientific lab automation) with concrete simulation infrastructure.
- Addresses genuinely hard contact dynamics (granular/powder physics) rarely modeled in manipulation benchmarks.

## Weaknesses

- A single-domain (organic chemistry) benchmark, with unclear transfer to broader dexterous-manipulation research.
- No baseline policy performance numbers were found in available sources.

## Open Questions

- What policies were evaluated, and what are baseline success rates?
- Is there sim-to-real validation on physical Tianyi 2.0 hardware, or is this sim-only?

## Significance

Opens a genuinely new application niche — scientific laboratory automation — for humanoid dexterous manipulation research, an area largely absent from prior benchmarks in this vault.

## Links

- [Paper](https://arxiv.org/abs/2606.31037)
