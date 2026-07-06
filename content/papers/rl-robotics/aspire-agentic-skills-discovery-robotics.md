---
title: "ASPIRE: Agentic Skills Discovery for Robotics"
date: 2026-06-30
topic: RL-Robotics
tags: [RL-Robotics, skill-discovery, code-as-policy, continual-learning, open-ended-learning, NVIDIA, zero-shot-generalization]
source: https://arxiv.org/abs/2607.00272
venue: "arXiv 2607.00272"
---

## Summary

ASPIRE (Agentic Skill Programming through Iterative Robot Exploration) is a continual learning system that autonomously writes and refines robot control programs in a code-as-policy paradigm while compounding experience into a reusable skill library. Three components operate in an open-ended loop: (1) a closed-loop robot execution engine with multimodal traces enabling autonomous failure diagnosis and repair, (2) a continually expanding skill library distilling validated fixes into reusable transferable knowledge, and (3) evolutionary search generating diverse task sequences to explore beyond single-trajectory refinement.

## Key Contributions

- Closed-loop execution engine with multimodal trace collection for automated failure diagnosis and repair synthesis
- Continually expanding skill library that distills validated code fixes into reusable primitives
- Evolutionary task sequence generation for broad exploration
- 77% improvement over prior methods on LIBERO-Pro under perturbation
- 72% improvement on Robosuite bimanual handover
- 32% improvement on BEHAVIOR-1K long-horizon household tasks
- Zero-shot generalization to unseen long-horizon tasks: 31% vs. 4% for prior methods on LIBERO-Pro Long
- Collaboration: NVIDIA, UMich, UIUC, UC Berkeley, CMU

## Significance

ASPIRE represents a major step toward autonomous robot skill acquisition—a system that improves itself through exploration, failure analysis, and skill reuse, with dramatic gains on challenging long-horizon manipulation benchmarks from top research institutions.

## Links

- [Paper](https://arxiv.org/abs/2607.00272)
- [Project](https://research.nvidia.com/labs/gear/aspire/)
