---
title: "VOMMI: Collecting and Leveraging Portable Demonstrations for Mobile Manipulation"
date: 2026-10-06
topic: VLA
tags: [vla, data-collection, mobile-manipulation, robotics, vla-posttraining]
source: https://arxiv.org/abs/2610.08220
venue: "arXiv"
---

## Summary

VOMMI is a low-cost, RGB-camera-only handheld capture system (estimated $100-200 in hardware) for collecting mobile-manipulation demonstrations without needing the actual robot, then using that portable data to train VLA policies. A policy trained solely on portable demonstrations shows 18.2% lower base-velocity error than one trained with robot-collected demonstrations, and the full system improves mean real-robot success by 8.3 points over OpenPI 0.5 (58.3% vs. 50.0%) across three tasks.

## Key Contributions

- A cheap (~$100-200), portable, fisheye-RGB-camera-based capture rig for mobile-manipulation demonstration collection, avoiding the need for the physical robot during data collection.
- Evidence that portable demonstrations can produce a lower base-velocity error policy than robot-collected demonstrations, suggesting the portable rig may capture smoother/cleaner human motion for locomotion control.
- Real-robot evaluation against OpenPI 0.5 across three tasks with a meaningful (8.3 point) success improvement.

## Strengths

- Dramatically lowers the cost and logistical burden of mobile-manipulation data collection by decoupling it from robot availability, directly addressing one of the biggest bottlenecks in scaling VLA training data.
- The counterintuitive finding that portable-only training beats robot-collected training on base-velocity error is a genuinely interesting result worth further scrutiny.

## Weaknesses

- Only 3 real-robot tasks evaluated, a fairly narrow test of generalization for a data-collection method meant to scale broadly.
- A large author list on a short, apparently preprint-stage paper suggests this may be an early report from a larger ongoing data-collection effort rather than a fully mature system.

## Open Questions

- How does the sim-to-real (or portable-to-robot) domain gap behave as task complexity increases beyond the three tested tasks?
- Can the portable capture rig be scaled to large crowdsourced data collection (similar to UMI-style approaches), and does quality hold up outside controlled lab conditions?

## Significance

A concrete, low-cost data-collection pipeline that directly tackles the scaling bottleneck for mobile-manipulation VLA training data, in the same spirit as UMI and other portable-demonstration efforts, but specifically targeting whole-body mobile manipulation rather than fixed-base arms.

## Links

- [Paper](https://arxiv.org/abs/2610.08220)
