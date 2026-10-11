---
title: "SMART: Zero-Shot Sim-to-Real Articulated Object Manipulation via Large-Scale Synthetic Pretraining"
date: 2026-10-06
topic: VLA
tags: [vla, synthetic-data, sim-to-real, robotics, vla-posttraining]
source: https://arxiv.org/abs/2610.07652
venue: "arXiv"
---

## Summary

SMART builds a large-scale simulation platform and dataset of over 1 million synthetic demonstrations spanning 44 atomic task types, 5 robot setups, and roughly 2,500 articulated objects (cabinets, microwaves, etc.), then pretrains a VLA on this purely synthetic data. The resulting model reports zero-shot sim-to-real transfer on real-world articulated-object manipulation tasks, with an overall average real-robot success rate of 76.7%.

## Key Contributions

- A large-scale synthetic demonstration dataset (1M+ trajectories) spanning many articulated object categories and multiple robot embodiments.
- A VLA pretrained entirely on synthetic data that transfers zero-shot to real articulated-object manipulation.
- Real-robot evaluation across multiple task types showing a 76.7% average success rate without any real-world fine-tuning.

## Strengths

- Zero-shot sim-to-real transfer at this scale (2,500+ objects, 44 task types) is a strong demonstration that synthetic data diversity can substitute for costly real-world data collection in this domain.
- Articulated objects (doors, drawers, appliances) are a historically hard manipulation category due to kinematic constraints, making this a meaningfully difficult testbed.

## Weaknesses

- Some internal inconsistency in the reported dataset statistics across different parts of the paper suggests the terminology around scene/object counts needs careful reading of the full text.
- Sim-to-real gap for articulated objects can be sensitive to contact dynamics and joint-friction modeling, which synthetic data may not capture perfectly even at scale; this isn't quantified separately in the available material.

## Open Questions

- How does performance scale with dataset size — is 1M+ demonstrations near a point of diminishing returns, or would even more synthetic data help further?
- Would mixing in even a small amount of real-world fine-tuning data close the remaining gap to in-domain real-trained baselines?

## Significance

Reinforces a 2026 trend (alongside InternData-A1, Sim2Real-VLA) that large-scale, diverse synthetic pretraining can be a viable substitute for real-world data collection for specific manipulation categories, which matters directly for scaling VLA training pipelines cheaply.

## Links

- [Paper](https://arxiv.org/abs/2610.07652)
