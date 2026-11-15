---
title: "SLA: Scaling Spatial-Language-Action Model via Continual Pre-training"
date: 2026-11-05
topic: VLA
tags: [spatial-reasoning, continual-pretraining, cross-embodiment, flow-matching]
source: https://arxiv.org/abs/2611.08373
venue: "arXiv"
---

## Summary

SLA argues that most VLA foundation models inherit purely 2D visual representations from vision-language pretraining, with 3D/spatial grounding only bolted on during task-specific fine-tuning. It addresses this by injecting spatial alignment — training intermediate visual embeddings to match features from a frozen 3D perception model — directly into a continual pretraining stage built on top of an already-pretrained π0.5 policy, then carrying that alignment signal through downstream post-training.

## Key Contributions

- A continual-pretraining recipe that adds spatial (3D-aligned) supervision on top of an existing generalist VLA (π0.5) rather than training spatial grounding from scratch, so pretrained weights and the original inference architecture are preserved (the 3D-alignment auxiliary head is dropped at inference).
- A curated, unified pretraining corpus combining six heterogeneous robot datasets (~1.7M episodes, ~14,330 hours) spanning diverse embodiments, tasks, and scenes, explicitly built to support spatial learning at scale.
- Reported state-of-the-art results on RoboDojo-Real, RoboTwin 2.0 (Clean2Random setting), RoboCasa-Panda, and LIBERO-Plus, plus a real-world deployment study across 8 conditions showing a 24.0-percentage-point average success-rate gain over the π0.5 baseline.

## Strengths

- The "spatial alignment only during training, standard architecture at inference" design is practical — it avoids inference-time latency or VRAM cost from an added 3D module while still letting spatial structure shape the learned representations.
- Building on an already-strong base policy (π0.5) and a large multi-dataset corpus gives the comparison against that same base policy real teeth (same inference architecture, so gains are more attributable to the added pretraining signal than to a confound in model capacity).
- Evaluation spans both simulation (RoboTwin 2.0, RoboCasa, LIBERO-Plus) and real-world multi-condition deployment, which is a more convincing generalization test than sim-only benchmarks.

## Weaknesses

- All headline numbers (RoboTwin 2.0 72.3%, RoboDojo-Real 33.9%, +24pp real-world gain) are self-reported by the authors with no independent reproduction yet; code/weights release appears partial (community trackers note the continual-pretraining raw data and part of the RoboDojo-Real reproduction were still pending at publication).
- The method depends on a frozen 3D perception model as a teacher signal, so SLA's spatial grounding is only as good as that external model's 3D representations — any systematic bias or failure mode in the 3D teacher could propagate into the policy without inference-time correction.
- Because SLA initializes from π0.5, the comparison baseline is tied to one specific base model family; it's unclear how the approach transfers to other VLA backbones (e.g., autoregressive or diffusion-action-head architectures).

## Open Questions

- How much of the real-world gain comes from the added data corpus scale versus the spatial-alignment loss itself — is there an ablation isolating the two?
- Does the 3D-alignment benefit hold for embodiments or camera configurations not represented in the six source datasets?
- Will the full training/continual-pretraining data and reproduction code be released, enabling independent verification of the reported SOTA numbers?

## Significance

SLA is a concrete data point in the broader trend of adding explicit 3D/spatial supervision to 2D-pretrained VLA backbones without changing inference-time architecture, and its large curated multi-embodiment corpus is itself a potentially reusable resource for future spatial-VLA work.

## Links

- [Paper](https://arxiv.org/abs/2611.08373)
- [Project Page](https://embodiedsla.github.io/)
