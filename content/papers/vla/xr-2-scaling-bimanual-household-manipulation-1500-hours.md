---
title: "Scaling Bimanual Household Manipulation from 1,500 Hours of Demonstrations to On-Policy Corrections"
date: 2026-09-03
topic: VLA
tags: [vla, bimanual-manipulation, data-scaling, dagger, on-policy-correction, vla-posttraining]
source: https://arxiv.org/abs/2609.03591
venue: "arXiv"
---

## Summary

This paper releases a 1,500-hour bimanual household manipulation dataset (531.7 hours of real-robot teleoperation across 32,518 trajectories, plus roughly 1,000 hours of UMI-collected demonstrations) and uses it to train XR-2, a 5B-parameter VLA model, via a purpose-built high-throughput data pipeline and multi-stage training paradigm. It then studies two scaling axes explicitly: growing the amount of expert demonstration data, and post-training with DAgger-style on-policy correction data collected from real-time human interventions.

## Key Contributions

- A large, task-diverse bimanual household manipulation dataset combining teleoperation and UMI-collected demonstrations at a scale (1,500 hours) uncommon outside a handful of industrial labs.
- A high-throughput data pipeline and multi-stage training paradigm engineered specifically for data efficiency at this scale, reported to retain favorable training efficiency despite the corpus size.
- A controlled empirical study of two distinct scaling axes — raw expert demonstration volume and on-policy DAgger correction volume — showing consistent, monotonic success-rate improvement across both, rather than just reporting a single scaled-up end result.

## Strengths

- Explicitly isolating demonstration-volume scaling from correction-volume scaling gives the field a rare direct comparison of "more offline data" versus "targeted online correction data," which is directly relevant to budgeting data-collection effort.
- Combining teleoperation with UMI (handheld gripper) data is a practical way to increase throughput and diversity beyond what teleoperation alone can achieve at this scale.
- The DAgger-correction results are a concrete, large-scale data point for the value of human-in-the-loop post-training, complementing existing DAgger-style methods in this space with far larger data volume than typical proof-of-concept studies.

## Weaknesses

- Bimanual household manipulation is a specific task family; it's unclear how the observed scaling trends generalize to other domains (industrial, outdoor, dexterous single-arm tasks).
- The paper doesn't appear to compare against alternative uses of the same collection budget (e.g., RL fine-tuning or simulation-augmented data) to establish whether DAgger correction is the most cost-effective use of marginal data-collection effort versus other post-training strategies.
- A 5B-parameter model and purpose-built pipeline represent significant infrastructure investment that may not be reproducible outside well-resourced labs, limiting independent verification of the scaling claims.

## Open Questions

- Does the observed scaling trend (steady, consistent improvement) show diminishing returns beyond 1,500 hours, or is the corpus still in the steep part of the scaling curve?
- How does the relative value of demonstration data versus DAgger correction data shift as the base policy becomes more competent?
- Would the same multi-stage training paradigm transfer to other embodiments, or is it tuned specifically for this bimanual platform?

## Significance

One of the largest reported bimanual manipulation corpora with an accompanying controlled scaling study, this paper provides useful empirical grounding for a question the field has mostly answered anecdotally: whether to invest additional data-collection budget in more offline demonstrations or in targeted on-policy human corrections.

## Links

- [Paper](https://arxiv.org/abs/2609.03591)
