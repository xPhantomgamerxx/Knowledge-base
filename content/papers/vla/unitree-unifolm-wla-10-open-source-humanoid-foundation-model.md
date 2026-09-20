---
title: "Unitree UnifoLM-WLA-1.0: Fully Open-Sourced Humanoid Foundation Model"
date: 2026-09-10
topic: VLA
tags: [humanoid, open-source, world-action-model, foundation-model]
source: https://unigen-x.github.io/unifolm-wla.github.io/
venue: "Official release (Unitree Robotics)"
---

## Summary

Unitree's major upgrade and full open-sourcing of its general-purpose humanoid foundation model: a ~6B-parameter model trained on roughly 2,500 hours of real-robot data that coordinates 64 desktop and whole-body manipulation tasks from a single set of weights, combining an embodied-reasoning/future-dynamic-region-prediction backbone (UnifoLM-ER-Flow) with an MMDiT action expert for discrete action decoding.

## Key Contributions

- Unifies desktop manipulation and whole-body mobile manipulation in one model supporting both two-finger grippers and multiple five-finger dexterous hands
- Combines embodied reasoning, future dynamic-region prediction, and discrete action learning in a single architecture (UnifoLM-ER-Flow backbone + MMDiT action expert)
- Reports new SOTA results among open-source models across multiple public embodied benchmarks, with claimed cross-task and cross-end-effector generalization from one checkpoint

## Strengths

- Broad task coverage (64 tasks) and cross-embodiment (gripper + multiple dexterous hands) from a single model is an ambitious generalization claim, if it holds up
- Full open-sourcing (once weights ship) would meaningfully lower the barrier to humanoid VLA research relative to closed frontier models

## Weaknesses

- At announcement time, code/weights/datasets are listed as "coming soon" — independent verification of the SOTA claims is not yet possible
- "Future dynamic-region prediction" is a distinctive architectural claim but detailed ablations/comparisons against pure world-model or pure VLA baselines are not yet public

## Open Questions

- How does UnifoLM-WLA-1.0 compare directly against GR00T N1.7, π0.7, or Gemini Robotics 2 on shared benchmarks once weights are released?
- Does the 2,500-hour real-data training regime generalize outside Unitree's own hardware/task distribution?

## Significance

A major open-source humanoid foundation model release from a leading hardware vendor, continuing the trend (alongside AgiBot, Xiaomi, GR00T) of hardware companies shipping their own general-purpose VLA/WAM stacks rather than relying solely on third-party models.

## Links

- [Blog](https://unigen-x.github.io/unifolm-wla.github.io/)
