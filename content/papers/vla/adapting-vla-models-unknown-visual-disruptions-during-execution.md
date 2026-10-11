---
title: "Adapting Vision-Language-Action Models to Unknown Visual Disruptions During Execution"
date: 2026-10-06
topic: VLA
tags: [vla, test-time-adaptation, robustness, robotics, vla-posttraining]
source: https://arxiv.org/abs/2610.07946
venue: "arXiv"
---

## Summary

This paper proposes SALT, a test-time adaptation method that uses the unexecuted remainder of a policy's own previous action chunk as a self-supervised training target when visual disruptions occur during execution, letting the policy adapt online without external supervision. On LIBERO-10, SALT raises average success under five persistent visual corruptions from 43.9% to 53.2% with SmolVLA and from 58.7% to 66.0% with GR00T N1.7, and on a real robot, task progress rose from 0.49 to 0.61 across digital and physical disruptions.

## Key Contributions

- A self-supervised test-time adaptation signal derived from the policy's own unexecuted action-chunk remainder, requiring no external labels or reward signal.
- Demonstrated gains across two different VLA backbones (SmolVLA, GR00T N1.7) on the same corruption benchmark.
- Real-robot validation under both digital (simulated corruption injected into the observation) and physical disruptions.

## Strengths

- The self-supervision source (unexecuted action-chunk remainder) is elegant: it requires no reward model, human feedback, or external supervision signal, making it broadly applicable at deployment.
- Consistent, substantial gains (roughly +9 and +7 points) across two different backbones strengthens the case that the method is general-purpose rather than backbone-specific.
- Both simulated (LIBERO-10) and real-robot evaluation, with both digital and physical disruption types tested on the real robot.

## Weaknesses

- Gains, while solid, still leave substantial absolute performance gaps (e.g., 53.2% and 66.0% are still well below clean-condition performance), so the method mitigates rather than solves the disruption problem.
- Test-time adaptation using the model's own predictions as a training target carries some risk of reinforcing systematic errors if the unexecuted-chunk assumption breaks down under certain disruption types.

## Open Questions

- Under what disruption conditions does the self-supervised signal become unreliable or actively harmful (error reinforcement), and can the method detect and avoid that regime?
- How does SALT's online adaptation compute/latency cost compare to the benefit, for real-time control loops?

## Significance

A practically important contribution to test-time robustness for VLA policies, an area (alongside StableVLA, RobustVLA, causality-aware test-time adaptation) that matters directly for real-world deployment where visual conditions inevitably drift from training distributions.

## Links

- [Paper](https://arxiv.org/abs/2610.07946)
