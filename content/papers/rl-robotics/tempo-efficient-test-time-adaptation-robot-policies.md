---
title: "Efficient Test-Time Adaptation For Robot Policies"
date: 2026-10-20
topic: RL-Robotics
tags: [rl-robotics, test-time-adaptation, locomotion, humanoid, vla-posttraining]
source: https://arxiv.org/abs/2610.20318
venue: "arXiv / NeurIPS 2026"
---

## Summary

Qualcomm AI Research proposes TEMPO, a test-time adaptation (TTA) method for RL-trained locomotion policies that keeps a frozen pretrained critic as a stand-in reward signal, adds an entropy regularizer on the critic's predictive distribution, and uses a prioritized-replay-style memory that spends compute on low-value observations via importance sampling. It targets the practical problem of on-device policy degradation under terrain, payload, or sensor shift without retraining.

## Key Contributions

- TEMPO: entropy-regularized, memory-guided actor-only updates that reuse a frozen critic instead of requiring a reward signal at deployment time.
- A score-based (prioritized) memory mechanism that concentrates adaptation compute on observations the critic scores poorly, rather than uniformly over the rollout.
- Evaluation across quadruped (Go1, Go2) and humanoid (G1) platforms in MuJoCo Playground, reporting up to ~80% improvement in single-device deployment settings.

## Strengths

- Actor-only, critic-frozen design is lightweight enough for plausible on-device deployment, addressing a real latency/memory constraint that most TTA-for-robotics work ignores.
- Tested across three embodiments (two quadrupeds, one humanoid) rather than a single robot, giving some embodiment-generality evidence.
- The entropy regularization plus importance-sampled memory is a sensible combination for stabilizing updates driven by a possibly-imperfect frozen critic.

## Weaknesses

- Relies entirely on simulation (MuJoCo Playground); no real-hardware validation is reported, so the on-device compute/latency claims that motivate the method are not actually demonstrated on a device.
- The frozen critic is the method's load-bearing component — the authors themselves note that severe critic miscalibration or large train/deploy domain mismatch degrades adaptation, which is exactly the regime where TTA is most needed.
- Numbers reported third-hand (e.g., 98.7 vs 89.8 average score, 14.6 vs 9.9 vs a "QMAX" baseline) are inconsistent across summaries and could not be verified against the primary PDF in this run due to arxiv.org being unreachable from this environment.

## Open Questions

- How does TEMPO degrade as the actual deployment distribution drifts further from the critic's training distribution — is there a principled way to detect when the critic itself needs updating?
- Would this transfer to manipulation or VLA-style policies, or is it specific to locomotion's relatively low-dimensional, cyclic action structure?
- No comparison to lightweight online RL fine-tuning baselines is mentioned beyond "QMAX" — how does TEMPO compare against simpler fallback strategies like safety-reflex controllers?

## Significance

A concrete, deployment-minded entry in the broader test-time-adaptation-for-robot-policies trend (alongside VLA-focused TTA/TTT work like Verify-Act-Distill and TTT-RM this cycle), notable for targeting the RL/locomotion side of the field rather than VLA manipulation, and for taking on-device compute constraints seriously as a design parameter rather than an afterthought.

## Links

- [Paper](https://arxiv.org/abs/2610.20318)
- [NeurIPS 2026 poster](https://neurips.cc/virtual/2026/poster/155174)
