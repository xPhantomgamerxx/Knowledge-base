---
title: "Towards Zero-Shot Transfer Across Embodiments For Driving VLAs"
date: 2026-09-02
topic: VLA
tags: [vla, autonomous-driving, cross-embodiment, zero-shot-transfer, bird's-eye-view]
source: https://arxiv.org/abs/2609.02341
venue: "arXiv"
---

## Summary

This paper studies whether VLA models trained for autonomous driving can transfer zero-shot to unseen datasets and camera rigs — a form of cross-embodiment generalization specific to the driving domain, where "embodiment" means sensor/camera configuration rather than robot morphology. It shows naively pooling more driving datasets into training does not reliably improve performance even within seen configurations, and proposes BEV-Forcing, an auxiliary objective that distills ground-plane object-layout knowledge from a specialized Bird's-Eye-View model into the VLA backbone.

## Key Contributions

- An empirical demonstration that multi-dataset training for driving VLAs is not a free lunch: adding more training datasets can fail to improve, or even hurt, performance on datasets already seen during training.
- BEV-Forcing, an auxiliary training objective that transfers spatial ground-plane layout understanding from a specialized BEV perception model into the VLA's backbone representations.
- Zero-shot transfer evaluation across unseen datasets and camera rigs, directly testing generalization rather than only in-distribution performance.

## Strengths

- Addresses a genuinely underexplored evaluation gap: most driving VLA papers report in-distribution results on a single benchmark and rarely test cross-dataset/cross-camera-rig zero-shot transfer.
- The BEV-Forcing idea is a pragmatic way to inject strong, well-understood geometric priors (from mature BEV perception literature) into a VLA without redesigning the backbone from scratch.
- The negative result on naive multi-dataset pooling is a useful cautionary finding for practitioners assuming "more data always helps."

## Weaknesses

- Scoped specifically to autonomous driving, so the transfer challenges (camera rig variation) are somewhat different in character from cross-embodiment transfer in manipulation (kinematics, DoF, gripper geometry) — findings may not generalize across those domains.
- Relies on a separately trained specialized BEV model as a teacher signal, adding a dependency and training-pipeline complexity rather than solving the problem end-to-end within the VLA itself.
- Evaluation is limited to the driving VLA setting; it's unclear whether BEV-Forcing-style auxiliary distillation would help general manipulation VLAs facing analogous camera-viewpoint variation.

## Open Questions

- Would an analogous auxiliary-objective approach (distilling a specialized perception model's geometric knowledge into the VLA backbone) help cross-embodiment transfer in manipulation settings, not just driving?
- What specifically causes multi-dataset pooling to hurt in-distribution performance — is it label/annotation inconsistency across datasets, or a more fundamental optimization interference?
- How does BEV-Forcing's benefit scale with the diversity of camera rigs seen during pretraining?

## Significance

A useful, somewhat contrarian data point for the broader cross-embodiment VLA literature: it shows that even within a single task domain (driving), embodiment/sensor-configuration transfer is not automatically solved by dataset scale, reinforcing the value of targeted auxiliary objectives over brute-force data pooling.

## Links

- [Paper](https://arxiv.org/abs/2609.02341)
