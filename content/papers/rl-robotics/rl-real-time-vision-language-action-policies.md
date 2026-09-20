---
title: "Reinforcement Learning for Real-Time Vision-Language-Action Policies"
date: 2026-09-16
topic: RL-Robotics
tags: [vla-posttraining, rl-fine-tuning, real-time-control, inference-latency, asynchronous-execution]
source: https://arxiv.org/abs/2609.18207
venue: "arXiv (Stanford)"
---

## Summary

From Stanford (Dong, Hung, Sadigh, Finn), this paper tackles a gap in RL fine-tuning of VLAs: large VLA models have high inference latency, so by the time an action is executed the observation it was selected on is stale, creating a distribution shift. Prior asynchronous-execution fixes were built for imitation learning only; this work extends real-time-compatible execution to RL fine-tuning.

## Key Contributions

- Identifies that RL fine-tuning methods for VLAs have generally ignored inference latency and the resulting observation staleness, unlike the imitation-learning literature which has addressed it via asynchronous execution
- Proposes an RL fine-tuning approach compatible with real-time control requirements of dynamic real-world manipulation, rather than just improving offline task success in latency-free simulation
- Positions RL fine-tuning as able to push policies beyond the training distribution toward higher reliability under real deployment latency constraints, unlike purely imitation-based asynchronous methods

## Strengths

- Addresses a genuinely underexplored and practically important gap — most VLA RL fine-tuning papers benchmark in settings that sidestep real inference latency entirely
- Strong authorship (Sadigh and Finn's groups have set much of the agenda for VLA RL fine-tuning), increasing likely rigor and follow-on impact

## Weaknesses

- As a very recent submission, no independent replication or extended community discussion is available yet
- Available material doesn't make fully clear the precise algorithmic mechanism (how latency-awareness is incorporated into the RL objective/critic) beyond the high-level framing

## Open Questions

- How much of the performance gain comes from RL itself versus from the latency-aware/asynchronous execution mechanism, i.e. would the same execution scheme also help a purely imitation-learned policy comparably?
- Does the approach generalize across different VLA backbone sizes, where latency scales with model size?

## Significance

Inference latency is one of the most cited practical blockers to deploying large VLA policies for dynamic, contact-rich, or fast-reacting tasks; bringing RL fine-tuning methods into a real-time-compatible regime is an important maturation step for the field.

## Links

- [Paper](https://arxiv.org/abs/2609.18207)
