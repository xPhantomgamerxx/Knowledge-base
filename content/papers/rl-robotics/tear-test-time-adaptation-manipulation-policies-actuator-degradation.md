---
title: "Test-Time Adaptation of Manipulation Policies Under Actuator Degradation"
date: 2026-09-28
topic: RL-Robotics
tags: [test-time-adaptation, hardware-robustness, policy-agnostic, vla-posttraining]
source: https://arxiv.org/abs/2609.36182
venue: "arXiv"
---

## Summary

TeAR (Telemetry-Aware Action Rectification) is a policy-agnostic wrapper that turns any frozen manipulation policy into a telemetry-conditioned one, rectifying its outgoing action using live per-joint temperature, current, and voltage readings before the action reaches the low-level controller. A lightweight Transformer learns to amplify, damp, or bias individual action components in response to actuator telemetry. Across 18 policy-task pairs spanning eight policy families and five manipulation tasks, TeAR adds +12% success on average over the frozen base policy, and improves success under heating by 10-15% on a physical arm with no on-robot fine-tuning.

## Key Contributions

- Policy-agnostic design: works as a wrapper around any of eight different policy families without requiring access to internals or retraining the base policy
- Uses real hardware telemetry (temperature, current, voltage) directly as the adaptation signal, rather than inferring degradation indirectly from visual or proprioceptive observation
- No on-robot fine-tuning needed to see the heating-robustness benefit, making it a drop-in addition to existing deployed policies

## Strengths

- Breadth of evaluation (18 policy-task pairs, 8 policy families, 5 tasks) is unusually thorough for a wrapper-style method, supporting the policy-agnostic claim more credibly than a single-backbone demonstration would
- Directly using actuator telemetry is a sensible, low-latency signal source compared to inferring hardware degradation from downstream task failure, which is slower and noisier
- Addresses a real and underserved operational problem (motor heating, current saturation, voltage sag) that affects long-duration or high-load deployments regardless of which policy is running

## Weaknesses

- +12% average success gain is solid but modest; for severely degraded actuators the rectification may not be sufficient to fully compensate, and the paper doesn't report a ceiling or failure point for how much degradation TeAR can handle
- Requires actuator telemetry access (temperature/current/voltage sensing) that not all robot platforms expose at the needed granularity, limiting immediate applicability
- As a learned Transformer rectifier, TeAR itself needs training data covering a range of degradation conditions — how that training data is obtained (simulated degradation? collected real degradation?) isn't detailed in the summary

## Open Questions

- How does TeAR's rectification interact with policies that are themselves adaptive (e.g., Self-Adaptive VLA) — do the two mechanisms compose, conflict, or overlap in function?
- What is the practical floor of actuator degradation beyond which rectification alone cannot compensate, and does TeAR degrade gracefully or fail abruptly past that point?

## Significance

Part of a notable late-2026 cluster of hardware-aware test-time adaptation work (alongside Self-Adaptive VLA) that shifts VLA/policy robustness research from purely software/perception concerns toward the physical realities of long-running deployed hardware.

## Links

- [Paper](https://arxiv.org/abs/2609.36182)
- [GitHub](https://github.com/somsagar07/TeAR-Telemetry-Aware-Action-Rectification)
