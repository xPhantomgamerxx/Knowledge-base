---
title: "Anticipation-VLA: Solving Long-Horizon Embodied Tasks via Anticipation-based Subgoal Generation"
date: 2026-05-11
topic: VLA
tags: [long-horizon, subgoal-generation, hierarchical, embodied-reasoning, compounding-errors]
source: https://arxiv.org/abs/2605.01772
venue: "arXiv 2605.01772"
---

## Summary

Anticipation-VLA tackles the compounding-error problem in long-horizon robotic tasks by introducing an Anticipation Model that adaptively and recursively generates future visual subgoals as intermediate planning targets. The hierarchical system pairs a fine-tuned Unified Multimodal Model for high-level subgoal generation with a goal-conditioned VLA policy for low-level action execution, continuously adapting subgoals as the task unfolds.

## Key Contributions

- Anticipation Model that recursively generates adaptive subgoal images, recalibrating predictions in response to evolving scene dynamics
- Hierarchical VLA architecture decoupling high-level visual planning from low-level motor control
- Demonstrated effectiveness in both simulated and real-world robotic manipulation benchmarks

## Significance

Addresses the fundamental long-horizon limitation of flat VLA architectures by adding structured visual foresight, showing that adaptive subgoal generation is essential for reliable long-horizon policy execution.

## Links

- [Paper](https://arxiv.org/abs/2605.01772)
- [HTML](https://arxiv.org/html/2605.01772v1)
