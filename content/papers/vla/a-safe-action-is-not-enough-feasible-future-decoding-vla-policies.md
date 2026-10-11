---
title: "A Safe Action Is Not Enough: Feasible-Future Decoding for Vision-Language-Action Policies"
date: 2026-10-04
topic: VLA
tags: [vla, safety, robotics]
source: https://arxiv.org/abs/2610.05166
venue: "arXiv"
---

## Summary

The authors identify a "feasibility-likelihood gap" in VLA safety: a frozen policy's action can be both safe and the most likely next move, yet leave no remaining policy-supported path to finishing the task safely. They derive an exact next-block "feasible-future mass" term to quantify this and propose VICS-G, a training-free reranker that uses it to steer action selection, reporting 1.9-57.5% reductions in mean cumulative safety cost across six Safety-CHORES settings while staying within 2.5 percentage points of normal sampling in task success.

## Key Contributions

- Formal identification and framing of the "feasibility-likelihood gap" distinct from simple action-level safety checks.
- A derived exact next-block marginal ("feasible-future mass") capturing whether safe task completion remains reachable after an action.
- VICS-G, a training-free reranker usable on top of any frozen VLA policy, evaluated across six Safety-CHORES settings.

## Strengths

- Training-free design means it can be layered onto existing deployed VLA policies without retraining.
- Conceptually distinguishes "locally safe" from "globally feasible toward safe completion," a more rigorous notion than instantaneous safety checks like collision avoidance alone.
- Reports success-rate cost (staying within 2.5 points of baseline) alongside the safety-cost reduction, rather than safety gains in isolation.

## Weaknesses

- The authors themselves note that all cost and violation confidence intervals in their Table 5 include zero, meaning the paper's own data does not statistically establish a real safety improvement — a notable self-reported limitation.
- Evaluated only on the Safety-CHORES simulation settings; no real-robot validation is mentioned in the available material.

## Open Questions

- Can the statistical uncertainty acknowledged by the authors be resolved with larger evaluation sample sizes or tighter experimental controls?
- How does VICS-G's computational overhead at inference time compare to simpler instantaneous safety filters like WBAG or VLSA/AEGIS?

## Significance

Contributes a more theoretically grounded notion of "feasible" versus merely "safe" actions to the fast-growing VLA safety literature, though its own honestly reported statistical caveats temper how much can be concluded from this particular study.

## Links

- [Paper](https://arxiv.org/abs/2610.05166)
