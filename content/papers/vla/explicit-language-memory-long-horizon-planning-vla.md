---
title: "Explicit Language Memory for Long-Horizon Planning in Vision-Language-Action Models"
date: 2026-08-04
topic: VLA
tags: [vla, long-horizon-planning, memory, hierarchical-control]
source: https://arxiv.org/abs/2608.04765
venue: "arXiv"
---

## Summary

Proposes a hierarchical long-horizon VLA architecture built around an explicit, human-readable language memory, rather than an opaque latent memory or KV-cache. At each decision step a high-level VLM reads the global instruction, current observation, and prior memory to emit an updated textual memory (summarizing completed milestones in past tense, retaining decision-relevant state) plus a concise subtask handed to the low-level action policy.

## Key Contributions

- An explicit, interpretable memory representation distinct from latent-memory approaches used elsewhere in the field.
- A memory-update protocol that ties subtask generation to accumulated, verbalized task state.
- Targets sparse-demonstration compositional generalization and closed-loop error accumulation over long horizons.

## Strengths

- Interpretability: memory state can be inspected directly rather than probed from a latent vector.
- Directly targets a known VLA failure mode — drift and error accumulation over long-horizon tasks.
- Decouples memory summarization from low-level control learning, simplifying each component's objective.

## Weaknesses

- Textual memory generation adds inference latency versus latent-memory approaches.
- Unclear how the approach handles state that is hard to verbalize (fine-grained contact/force information).
- No direct quantitative comparison against the vault's existing latent-memory VLAs (ECHO, MemoryVLA++) could be confirmed from available sources.

## Open Questions

- How does textual memory compare quantitatively to latent-memory long-horizon methods on shared benchmarks?
- What is the added inference cost of maintaining and re-reading a textual memory at each step?
- Does the approach generalize across embodiments and task families beyond what was evaluated?

## Significance

Adds an interpretable alternative to the growing cluster of memory-augmented VLA work, trading some efficiency for transparency in how the policy tracks long-horizon task state.

## Links

- [Paper](https://arxiv.org/abs/2608.04765)
