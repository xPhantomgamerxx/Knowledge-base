---
title: "DexVerse: A Modular Benchmark for Multi-Task, Multi-Embodiment Dexterous Manipulation"
date: 2026-07-14
topic: RL-Robotics
tags: [benchmark, dexterous-manipulation, multi-task, multi-embodiment, visuomotor, teleoperation, evaluation]
source: https://arxiv.org/abs/2607.08751
venue: "arXiv 2607.08751"
---

## Summary

DexVerse is a large-scale modular benchmark covering 100 dexterous manipulation tasks spanning grasping, relocation, articulated-object interaction, tool use, bimanual coordination, nonprehensile control, multi-goal execution, and long-horizon multi-stage completion. It supports 3 robot arms and 6 dexterous hands, with configurable visual variations (texture, background, lighting, viewpoint) for visuomotor generalization evaluation.

## Key Contributions

- 100 diverse tasks covering the full breadth of dexterous manipulation interaction modes
- 3 robot arms × 6 dexterous hands for multi-embodiment evaluation
- 3,180 expert demonstrations with synchronized proprioceptive, RGB, depth, point-cloud, and state observations collected via VR teleoperation
- Configurable visual variation for systematic sim-to-real and cross-domain generalization assessment
- Extensible design: new tasks, assets, and embodiments can be added via modular task API

## Significance

Addresses a critical gap in the field — prior benchmarks remain limited in task diversity, embodiment coverage, or controllable visual variation — providing a comprehensive and reproducible evaluation platform for the next generation of dexterous robotic policies.

## Links

- [Paper](https://arxiv.org/abs/2607.08751)
