---
title: "Skills in Weights, Memory in Code: Hybrid Learning for Memory-Dependent Robot Manipulation (HyMeS)"
date: 2026-08-10
topic: VLA
tags: [vla, memory, long-horizon, hybrid-architecture, coding-agent]
source: https://arxiv.org/abs/2608.09410
venue: "arXiv"
---

## Summary

HyMeS targets non-Markovian, memory-dependent manipulation where standard VLAs (acting on current observation or short history) fail. Low-level motor skills are learned via standard gradient-based imitation learning on a Markovian VLA, while a coding agent separately learns high-level memory-management strategies — iteratively updating an executable heuristic system from rollout feedback — so demonstrations are needed only for reusable motor skills, not every history-dependent task configuration.

## Key Contributions

- Separates "skills" (encoded in VLA weights) from "memory management" (encoded in executable code learned by a coding agent).
- Reduces the demonstration burden for long-horizon, memory-dependent tasks relative to end-to-end memory-augmented VLAs.
- Aims for compositional generalization across history-dependent task configurations without retraining the base policy.

## Strengths

- A genuinely novel division of labor between neural skill weights and symbolic/code-based memory logic.
- Claimed to be more data-efficient than dense end-to-end memory-augmented VLA baselines.

## Weaknesses

- Relies on a capable coding agent (likely an LLM) for memory-management heuristics, adding a new dependency and potential brittleness.
- No concrete success-rate numbers were available to verify the efficiency claim.
- Errors in agent-authored memory code could propagate unpredictably into policy failures.

## Open Questions

- How well does the heuristic-learning loop scale to longer or more complex interaction histories?
- How robust are code-generated heuristics to distribution shift in task structure?
- How does HyMeS compare quantitatively against the vault's existing latent-memory VLAs (ECHO, MemoryVLA++, HiMem-WAM)?

## Significance

Offers a structurally different answer to long-horizon memory than the latent-memory architectures dominating this vault's coverage, trading a new dependency (a coding agent) for an explicit, potentially more debuggable memory representation.

## Links

- [Paper](https://arxiv.org/abs/2608.09410)
