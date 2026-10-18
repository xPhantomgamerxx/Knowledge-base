---
title: "CoRE-VLA: Towards Scalable and Robust Vision-Language-Action Modeling via Conditional Routing of Experts"
date: 2026-10-09
topic: VLA
tags: [vla, mixture-of-experts, robustness, multimodal-fusion]
source: https://arxiv.org/abs/2607.03693
venue: "arXiv"
---

## Summary

CoRE-VLA addresses a specific brittleness in current VLA policies: they tie action generation to a fixed sensor configuration via shared dense computation, so missing or degraded sensors (e.g., a dropped depth stream) cause disproportionate performance loss. CoRE-VLA instead routes to modality-specialized experts gated by sensor availability, and to task-relevant experts gated by task intent.

## Key Contributions

- A conditional mixture-of-experts design where sensor availability (not just task) determines which experts are active, letting the model degrade gracefully when a modality (depth, in the paper's main setup) is missing at test time.
- Task-intent-conditioned routing on the action side, allowing specialization by task type rather than forcing one dense pathway to cover all tasks.
- Evaluation spanning LIBERO, RoboCasa GR1 Tabletop, and real dual-arm manipulation, including zero-shot generalization settings.

## Strengths

- Explicitly designing for sensor dropout (rather than assuming a fixed, always-available sensor suite) targets a real deployment risk that most VLA benchmarks don't test for.
- The reported routing behavior — expert usage shifting over a rollout and staying moderately balanced rather than collapsing to one expert — is a meaningful robustness signal, since MoE collapse is a known failure mode in other domains.

## Weaknesses

- The main auxiliary modality studied is depth; it's unclear how well the sensor-conditional routing generalizes to other common failure modes (e.g., tactile dropout, camera occlusion, wrist-camera-only setups).
- Mixture-of-experts architectures add inference-time routing overhead and complexity relative to a single dense VLA backbone, which matters for latency-sensitive real-time control.

## Open Questions

- How does CoRE-VLA's zero-shot generalization compare against simpler sensor-dropout-robust training recipes (e.g., modality-dropout data augmentation on a dense model) rather than architectural MoE routing?
- Does the approach scale cleanly to many more sensor modalities (tactile, audio, proprioception-only fallback) without a combinatorial blow-up in expert count?

## Significance

A concrete answer to the "what happens when a sensor drops out" robustness question that's increasingly relevant as VLA policies move from curated lab sensor rigs toward more heterogeneous, failure-prone real-world hardware.

## Links

- [Paper](https://arxiv.org/abs/2607.03693)
