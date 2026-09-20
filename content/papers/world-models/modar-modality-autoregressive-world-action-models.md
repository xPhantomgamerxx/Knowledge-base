---
title: "Modality-Autoregressive World-Action Models (ModAR)"
date: 2026-09-15
topic: WorldModels
tags: [multimodal-prediction, world-action-model, representation-learning, efficiency, ablation-study]
source: https://arxiv.org/abs/2609.17524
venue: "arXiv"
---

## Summary

A systematic, trained-from-scratch study of which future visual modalities (RGB, depth, DINO features, point tracks) actually help World Action Models, introducing ModAR — the first WAM to autoregressively denoise multiple future modalities in sequence before predicting actions — and finding that point tracks, DINO features, and depth help, while future-RGB prediction (the default target of most WAM work) provides no consistent benefit.

## Key Contributions

- A controlled ablation isolating modality choice from pretraining-backbone choice, unlike most prior WAM papers which conflate the two
- ModAR architecture: autoregressive cross-modal denoising so later-predicted modalities condition on earlier ones within the same forward pass
- Evidence that RGB prediction provides no consistent benefit once point tracks/features/depth are predicted
- Efficiency result: matches/beats fine-tuned video-pretrained baselines (75% vs. 72% success) using ~20x fewer training FLOPs and no video pretraining

## Strengths

- Legitimately field-relevant finding: an enormous fraction of the WAM literature is built on the premise that predicting future RGB video is the right supervisory signal, and this provides controlled counter-evidence
- The ~20x FLOP reduction with no pretraining is a strong claim, since pretraining cost is the biggest practical barrier to WAM adoption outside large labs
- Validated on three real-world bimanual tasks, with further gains shown from added human video data

## Weaknesses

- Trained-from-scratch vs. fine-tuned-baseline comparisons can be confounded by how much effort went into the baseline's fine-tuning recipe
- The "RGB doesn't help" finding may be task-specific — it's unclear if it holds for highly deformable/visually-rich tasks where appearance may carry more task-relevant signal than geometry
- Modality choice depends on the point-tracking/feature-extraction pipelines used to generate targets, which have their own failure modes (e.g., tracker drift) not discussed

## Open Questions

- Does the "geometry/semantics over RGB" finding generalize to deformable-object or liquid-handling tasks?
- How does ModAR's cost scale as more predicted modalities are added — is there a point of diminishing or negative returns?

## Significance

A rare paper in this saturated sub-area that challenges a widely shared default assumption (RGB prediction as the WAM training signal) with controlled evidence rather than proposing another WAM variant, potentially redirecting how future WAMs choose their prediction targets.

## Links

- [Paper](https://arxiv.org/abs/2609.17524)
