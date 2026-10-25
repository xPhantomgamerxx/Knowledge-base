---
title: "Fast-VLA: You Only Think Once for Robot Manipulation"
date: 2026-10-15
topic: VLA
tags: [vla, efficiency, inference-speed, task-memory, action-chunking]
source: https://arxiv.org/abs/2610.21389
venue: "arXiv"
---

## Summary

Fast-VLA attacks VLA inference latency by splitting "understanding the task" from "executing it." Instead of running a large VLM backbone on every control step (or even every action chunk), a frozen 4B-parameter VLM is run exactly once per episode to distill a fixed key-value "task memory." A much smaller online actor (184.7M params single-arm, 272M params bimanual) then handles all subsequent control purely by querying that cached memory against live observations, producing 50-step action chunks without ever re-invoking the large model.

## Key Contributions

- A "think once, act many" architecture that amortizes the cost of the large VLM over an entire episode rather than every inference step, versus prior VLAs that keep the VLM in the control loop continuously or periodically.
- A lightweight actor that cross-attends into the frozen task-memory KV cache, letting a small model stay reactive to live observations while leaning on the large model's language/scene understanding captured at the start of the episode.
- Reported amortized inference speedups of roughly 11–17x over continually-conditioned baselines on RoboTwin 2.0, with per-step latency around 1.4ms vs. ~16ms for a comparable baseline (DM0.5).
- Reported success rates around 92% on RoboTwin 2.0 and 96% on LIBERO, suggesting the amortization doesn't come at a large accuracy cost on these benchmarks.

## Strengths

- The core bet — that most of a VLM's useful contribution to a manipulation episode is fixed semantic/task understanding computed once at the start, not something that needs re-deriving every control step — is a reasonable and testable hypothesis, and the benchmark numbers are consistent with it holding on short, well-specified tasks.
- The latency numbers are large enough to matter for real-time control (single-digit millisecond per-step cost opens up control rates that a continually-conditioned 4B VLM cannot hit on typical onboard compute).
- Because the large VLM only runs once, this architecture is naturally compatible with running the expensive model off-robot/in the cloud at episode start, while the small actor runs fully on-device — a practical deployment pattern.

## Weaknesses

- The "think once" assumption is a liability for any task where the scene changes in ways that matter semantically mid-episode (a new obstacle appears, an instruction needs re-interpretation after a failure, a container is discovered to be different than expected) — the frozen task memory has no mechanism to update.
- RoboTwin 2.0 and LIBERO tasks are comparatively short-horizon; it's unclear whether a single task-memory snapshot remains sufficient for long-horizon or multi-stage tasks where "what the task means" effectively evolves as sub-goals are completed.
- The headline speedup figures come from a single paper's own baselines and haven't been independently reproduced; "DM0.5" as a baseline name suggests a close relative of π0.5-style diffusion/flow heads, but the comparison's fairness (equal training budget, equal model capacity for the baseline) is not something available in third-party summaries.

## Open Questions

- What happens on failure recovery — if the small actor gets into a state the frozen task memory didn't anticipate, is there any fallback to re-invoking the large VLM mid-episode?
- How sensitive is downstream performance to the task-memory's fixed size — would harder, more cluttered scenes need a larger KV cache, and does that reintroduce the latency the method is designed to avoid?
- Does this architecture transfer to settings with higher-frequency environmental change (dynamic obstacles, human-in-the-scene collaboration) where "think once" is more clearly the wrong inductive bias?

## Significance

Inference latency is one of the more concrete blockers to deploying large VLA backbones on real-time control loops, and decoupling one-time semantic understanding from a fast reactive actor is a clean, if task-horizon-limited, way to buy back most of a large model's latency cost.

## Links

- [Paper](https://arxiv.org/abs/2610.21389)
