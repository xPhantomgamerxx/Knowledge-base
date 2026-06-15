---
title: "Making Foresight Actionable: Repurposing Representation Alignment in World Action Models"
date: 2026-06-10
topic: WorldModels
tags: [world-action-model, representation-alignment, AGRA, video-diffusion, action-grounding, HKU, XPENG]
source: https://arxiv.org/abs/2606.12217
venue: "arXiv 2606.12217"
---

## Summary

This paper diagnoses a core failure mode in World Action Models (WAMs): the hidden states optimised for visual reconstruction are not inherently organised in a form useful for low-level action control. Through action-head attention analysis and causal interventions, the authors show that WAM action decoders fail to focus on task-relevant regions and remain sensitive to task-irrelevant perturbations. They propose AGRA (Action-Grounded Representation Alignment), an auxiliary objective that regularises the world-action interface by aligning intermediate video diffusion features with spatially coherent semantic representations from a foundation visual encoder.

## Key Contributions

- Attention analysis and causal interventions revealing the representation mismatch at the video-to-action interface in existing WAMs
- AGRA: an auxiliary representation-alignment objective applied at the world-action interface without requiring architectural changes to the base WAM
- Alignment of video diffusion features to a semantic foundation encoder improves spatial specificity and task-relevance in action decoding
- Consistent improvements in manipulation task success rate across multiple WAM baselines from The University of Hong Kong and XPENG Robotics

## Significance

Identifies and fixes a fundamental impedance mismatch between visual-fidelity world model representations and action-control requirements, providing a principled plug-in improvement applicable to any WAM with a video diffusion backbone.

## Links

- [Paper](https://arxiv.org/abs/2606.12217)
- [HTML](https://arxiv.org/html/2606.12217)
