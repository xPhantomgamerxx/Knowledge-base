---
title: "ECHO: Continuous Hierarchical Memory for Vision-Language-Action Models"
date: 2026-05-01
topic: VLA
tags: [memory, hierarchical, hyperbolic-space, long-horizon, LIBERO, experience-consolidation]
source: https://arxiv.org/abs/2605.10993
venue: "arXiv 2026"
---

## Summary

ECHO (Experience Consolidation and Hierarchical Organization) is a novel memory framework that operates in a Continuous Hierarchical Space to overcome memory capacity limitations in VLA models during long-horizon manipulation. Using a hyperbolic autoencoder, ECHO maps VLA hidden states into hyperbolic space and organizes experience vectors into a semantic memory tree with entailment constraints, enabling efficient top-down retrieval of relevant past experiences during task execution.

## Key Contributions

- Continuous Hierarchical Space for memory using hyperbolic geometry, enabling semantic organization of experience vectors
- Hyperbolic autoencoder that maps VLA hidden states to hyperbolic space with entailment constraints
- Semantic memory tree structure supporting efficient top-down retrieval
- Validated on all four standard LIBERO suites (Spatial, Object, Goal, Long) and real-world robotic platform

## Significance

Provides a principled solution to the memory capacity bottleneck in VLAs for long-horizon tasks, using geometric structure (hyperbolic space) to organize and retrieve experiences more effectively than flat memory approaches.

## Links

- [Paper](https://arxiv.org/abs/2605.10993)
