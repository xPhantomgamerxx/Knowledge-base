---
title: "Learning to Act While Waiting: RL Finetuning of Generalist Robot Policies Under Inference Latency"
date: 2026-09-27
topic: RL-Robotics
tags: [rl-robotics, vla, online-rl, inference-latency, vla-posttraining]
source: https://arxiv.org/abs/2608.23831
venue: "arXiv"
---

## Summary

This paper identifies that large generalist VLA policies' inference latency breaks the Markov assumption standard RL algorithms rely on, causing RL fine-tuning to fail outright when combined with realistic inference delays. It introduces ARLI (Asynchronous RL with Intermediate Information), which builds on latency-hiding asynchronous inference and restores near-Markovian structure via state augmentation with committed actions and a mid-inference observation, enabling RL fine-tuning to work under latency where it previously collapsed.

## Key Contributions

- Identifies and formalizes a previously under-examined failure mode: inference latency in large policies violates RL's Markov assumption, not just execution smoothness.
- ARLI's state augmentation (incorporating already-committed actions and a mid-inference observation) gives the RL agent the information it needs to act consistently with the true, latency-affected environment dynamics.
- Demonstrates that the latency-aware method not only fixes the failure but can match or exceed standard RL performance even in idealized zero-latency settings.

## Strengths

- Addresses a deployment-critical, previously underserved problem: most RL-for-VLA papers implicitly assume negligible inference latency, which is unrealistic for large generalist backbones running on real hardware.
- The claim that the method matches/exceeds no-latency RL performance is a strong result if it holds broadly, since it implies no fundamental trade-off between latency-robustness and peak performance.
- Multi-institutional collaboration (Berkeley, ETH Zurich, Microsoft, Siemens) suggests cross-validation across different robotics stacks/hardware.

## Weaknesses

- The approach depends on asynchronous inference architectures being already in place; teams with synchronous action-execution pipelines would need non-trivial re-engineering to adopt it.
- Results are likely to be sensitive to the specific latency distribution assumed (fixed vs. variable delay); real hardware often has more erratic latency spikes than clean benchmarks capture.
- No indication of how the approach scales to even larger models where latency grows further, or whether the state-augmentation trick remains sufficient as the mismatch between decision frequency and control frequency widens.

## Open Questions

- How does ARLI perform under highly variable, bursty latency (e.g., shared GPU inference serving multiple robots) rather than roughly constant latency?
- Can the state-augmentation technique be generalized to offline RL / offline-to-online settings, or is it specific to fully online fine-tuning?
- Does this approach compose with other post-training methods (e.g., reward shaping, human corrections) that were designed without latency in mind?

## Significance

This is a foundational fix for a problem that will only get worse as generalist VLA policies grow larger and slower: without latency-aware RL, online fine-tuning of frontier-scale robot policies risks silently failing in exactly the deployment settings where it matters most.

## Links

- [Paper](https://arxiv.org/abs/2608.23831)
