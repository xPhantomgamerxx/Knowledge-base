---
title: "PrimitiveVLA: Learning Reusable Motion Primitives for Efficient and Generalizable Robotic Manipulation"
date: 2026-05-28
topic: VLA
tags: [vla, motion-primitives, data-efficiency]
source: https://arxiv.org/abs/2605.28634
venue: "arXiv"
---

## Summary

PrimitiveVLA reframes VLA learning as a "disassemble and assemble" process over reusable motion primitives instead of directly mapping instructions to low-level control. A shared canonical representation plus a VLM planner assemble primitives closed-loop at inference, and the method reportedly beats a 100%-data baseline using only 50% of the training data on LIBERO.

## Key Contributions

- Decomposes demonstration trajectories into a library of reusable motion primitives rather than treating each demonstration as an undecomposed instruction-to-action mapping.
- A VLM-based planner sequences and assembles primitives closed-loop at inference time, rather than committing to a fixed plan upfront.
- A reported 2x data efficiency gain (matching a 100%-data baseline with 50% of the data) on LIBERO.

## Strengths

- Primitive decomposition is a long-standing idea in robotics (from classical motion planning through hierarchical RL) and reframing modern VLA training around it is a reasonable way to inject useful inductive bias and improve data efficiency.
- Closed-loop primitive assembly at inference (rather than open-loop plan execution) should make the system more robust to execution-time deviations than a fixed high-level plan.

## Weaknesses

- The quality of the entire system is gated by how well demonstrations decompose into a reusable primitive library; tasks that don't factor cleanly into discrete primitives (continuous, non-compositional motions) may not benefit or could even be hurt by forcing a primitive-based decomposition.
- The 50%-data-matches-100%-baseline result is reported on LIBERO, a simulation benchmark with a relatively constrained task/primitive distribution; it's unclear how the primitive library would need to scale for open-ended real-world task diversity.

## Open Questions

- How is the primitive library constructed and how does its size/coverage scale with task diversity — is it fixed after training or can new primitives be added incrementally?
- What is the closed-loop VLM planner's latency overhead, and is it compatible with real-time control?
- Does the data-efficiency gain hold on real robots and outside LIBERO's task distribution?

## Significance

A data-efficiency-focused contribution to the VLA literature that revives primitive-based decomposition as a way to reduce the demonstration burden — relevant given how central data scarcity remains as a bottleneck for generalist policies.

## Links

- [Paper](https://arxiv.org/abs/2605.28634)
