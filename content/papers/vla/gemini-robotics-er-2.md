---
title: "Gemini Robotics ER 2"
date: 2026-07-30
topic: VLA
tags: [embodied-reasoning, orchestration, multi-robot, official-release]
source: https://blog.google/innovation-and-ai/models-and-research/google-deepmind/gemini-robotics-er-2/
venue: "Google DeepMind (official blog)"
---

## Summary

Google DeepMind's upgraded embodied-reasoning "high-level brain" model (built on Gemini 3.5 Flash), launched alongside sibling models Gemini Robotics 2 (whole-body VLA controller) and Gemini Robotics On-Device 2. ER 2 handles real-time video understanding, task-progress tracking, and multi-robot coordination, delegating low-level motor execution to separate action models.

## Key Contributions

- Separates high-level embodied reasoning/planning from low-level action execution, letting the same reasoning model orchestrate different robot bodies (stationary arms through walking humanoids)
- Adds real-time streaming video understanding and lower-latency orchestration via the Gemini Live API, plus external tool/API calling (e.g., web search) mid-task
- Reports concrete benchmark numbers: 91.3% accuracy with 0.96s mean absolute distance on moment-finding, 57.4% accuracy on 5-band task-progress classification

## Strengths

- The reasoning/action separation is architecturally sensible and mirrors a broader industry trend (hierarchical "brain + action expert" stacks) also seen in τ0-VLA and other vault entries
- Public API availability (Gemini API / AI Studio) makes this immediately testable by third parties, unlike many research-only releases

## Weaknesses

- Reported task-progress classification accuracy (57.4% across 5 bands) is fairly modest, suggesting fine-grained progress tracking remains a hard open problem even for a frontier model
- As a closed/proprietary model, reproducibility and independent scrutiny of the benchmark numbers is limited

## Open Questions

- How does the ER 2 + action-model split perform versus end-to-end VLA controllers on tasks requiring tight reasoning-action coupling (e.g., reactive manipulation)?
- What is the latency/cost overhead of routing through Gemini Live API orchestration versus on-device hierarchical stacks?

## Significance

A notable frontier-lab data point on the industry's convergence toward hierarchical "reasoning brain + action model" architectures for physical AI, distinct from (though released alongside) the whole-body VLA controller already logged in the vault.

## Links

- [Blog](https://blog.google/innovation-and-ai/models-and-research/google-deepmind/gemini-robotics-er-2/)
