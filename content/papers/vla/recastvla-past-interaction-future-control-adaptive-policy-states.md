---
title: "RecastVLA: From Past Interaction to Future Control with Adaptive Policy States"
date: 2026-09-26
topic: VLA
tags: [vla, test-time-training, flow-matching, memory, vla-posttraining]
source: https://arxiv.org/abs/2609.32155
venue: "arXiv"
---

## Summary

RecastVLA maintains an adaptive policy state inside a flow-matching VLA via action-side test-time training (building on the RoboTTT line of work), letting the robot retain information about past interactions that are no longer visible in the current scene. Evaluated across LIBERO, RoboTwin, RoboDojo, and twelve real-robot tasks, with a 10.68-point success improvement on the RoboTwin Clean-to-Clean setting.

## Key Contributions

- Extends test-time training from pure context-scaling (RoboTTT) to an explicit, updatable "policy state" that persists task-relevant history
- Action-side (rather than observation-side) test-time training formulation, which sidesteps needing to re-render or re-encode stale visual context
- Broad evaluation spanning three simulated benchmarks plus twelve real-robot tasks

## Strengths

- Directly targets a known VLA failure mode: tasks where the relevant state (e.g., "I already picked up the first object") leaves the camera frame and standard reactive policies lose track
- The breadth of evaluation (sim + real, multiple benchmark suites) is unusually thorough for a test-time-training paper
- Builds incrementally and legibly on RoboTTT rather than introducing an unrelated mechanism, making the marginal contribution easy to assess

## Weaknesses

- "Adaptive policy state" risks silently accumulating stale or incorrect beliefs if early-episode errors propagate forward; the paper doesn't report failure-mode analysis for this risk
- Gains are reported as averages; task-level variance (where does it help most/least) isn't broken out in the summary, making it hard to predict applicability to a new task
- As with most test-time-training work, the added recurrent-state update at both train and inference time adds engineering complexity and training instability risk not deeply discussed

## Open Questions

- How does policy-state drift get corrected (or does it) over very long-horizon tasks exceeding the evaluated settings?
- How does this compare directly against retrieval-based memory approaches (e.g., T²Mem, Retrieve-then-Steer) on the same benchmarks?

## Significance

Part of a fast-moving cluster of 2026 work (RoboTTT, T²Mem, SCOUT, TeAR) establishing test-time adaptation/training as a standard tool for VLA robustness, moving the field beyond static post-trained policies toward policies that keep learning during deployment.

## Links

- [Paper](https://arxiv.org/abs/2609.32155)
