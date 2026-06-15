---
title: "AffordanceVLA: A Vision-Language-Action Model Empowering Action Generation through Affordance-Aware Understanding"
date: 2026-06-05
topic: VLA
tags: [affordance, intermediate-representation, mixture-of-experts, spatial-grounding, data-augmentation, VLA]
source: https://arxiv.org/abs/2606.06155
venue: "arXiv 2606.06155"
---

## Summary

AffordanceVLA addresses the structural mismatch between VLM semantic feature spaces and robot action spaces by introducing structured affordance forecasting as a task-oriented intermediate representation. Three complementary modules — Which2Act (object-centric visual latent grounding), Where2Act, and How2Act — are integrated into a Mixture-of-Transformer (MoT) architecture with specialized experts that bridge high-level scene semantics to precise low-level control.

## Key Contributions

- Which2Act: object-centric grounding via visual latent prediction that suppresses task-irrelevant distractors
- Three-component affordance framework (Which/Where/How2Act) providing spatially grounded, semantically conditioned, and action-coupled intermediate representations
- Mixture-of-Transformer (MoT) architecture with task-specific expert routing trained via a three-stage progressive data curriculum
- Automated affordance data-augmentation pipeline to overcome the scarcity of dense affordance labels in standard robot datasets

## Significance

Bridges the semantic-to-motor gap in VLAs by decomposing action generation into structured affordance sub-problems, yielding more interpretable and precise manipulation policies without requiring privileged 3D or depth information.

## Links

- [Paper](https://arxiv.org/abs/2606.06155)
- [HTML](https://arxiv.org/html/2606.06155)
- [GitHub](https://github.com/Skywalker-yqz/AffordanceVLA)
