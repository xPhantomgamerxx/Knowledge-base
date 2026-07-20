---
title: "Harness VLA: Steering Frozen VLAs into Reliable Manipulation Primitives via Memory-Guided Agents"
date: 2026-07-14
topic: VLA
tags: [vla, agentic, memory, long-horizon, test-time-adaptation, analytic-primitives, ieee-ral]
source: https://arxiv.org/abs/2607.08448
venue: "arXiv 2607.08448 / IEEE RA-L vol. 11 no. 8 (Aug 2026)"
---

## Summary

Harness VLA is a memory-augmented agentic framework that treats frozen VLA models as reliable visuomotor primitives and wraps them with an agentic planner. The planner handles scene staging, semantic re-targeting, long-horizon composition, and navigation using a small library of analytic primitives (MOVE TO, ROTATE WRIST, NAVIGATE TO), while delegating contact-rich execution to the frozen VLA. Past solutions discovered through autonomous interaction are stored in episodic memory for retrieval and reuse.

## Key Contributions

- Agentic planner + analytic primitives: separates non-contact structural reasoning from contact-rich visuomotor control
- Memory-guided solution reuse: discovered orchestration strategies stored and retrieved by the planner across episodes
- Frozen backbone: no retraining of the VLA model; the framework works around its deployment-shift failure modes
- Addresses embodied asymmetry: monolithic VLAs excel at contact-rich control but fail on semantic retargeting/layout shifts

## Significance

Demonstrates that frozen VLAs can be made robust to deployment shifts without fine-tuning by pairing them with a lightweight memory-guided agentic planner — a practical route to reliable long-horizon manipulation with existing model checkpoints.

## Links

- [Paper](https://arxiv.org/abs/2607.08448)
