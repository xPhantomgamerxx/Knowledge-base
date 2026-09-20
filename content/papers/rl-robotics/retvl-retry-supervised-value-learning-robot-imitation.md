---
title: "Beyond Monotonic Progress: Retry-Supervised Value Learning for Robot Imitation (ReTVL)"
date: 2026-07-06
topic: RL-Robotics
tags: [reward-modeling, value-learning, imitation-learning, mistake-recovery]
source: https://arxiv.org/abs/2606.24633
venue: "arXiv"
---

## Summary

ReTVL learns value functions from mixed-quality human demonstrations by treating "retry" segments (imprecise grasps, misalignment, repeated attempts) as informative supervision rather than noise, using sparsely annotated retry keypoints to teach the value function both coarse task progress and local mistake-recovery structure.

## Key Contributions

- Identifies that standard progress/value models assume monotonic task progress and therefore systematically ignore corrective/retry behavior common in real demonstrations
- Combines global progress calibration with retry-induced preference learning from sparse retry-keypoint annotations
- Learns a "mistake-sensitive" value function intended to better support downstream RL/imitation use

## Strengths

- Reframes a common data-quality problem (imperfect demos with corrections) as a supervision opportunity instead of something to filter out
- Conceptually complementary to standard progress-reward approaches rather than a wholesale replacement

## Weaknesses

- Requires sparse retry-keypoint annotation, adding a labeling step that pure imitation pipelines avoid
- Not clear how well it generalizes to demonstrations with subtle or unlabeled retries, or how annotation quality affects downstream value-function reliability
- Evaluation scope/benchmarks not detailed in accessible material, making it hard to judge generality

## Open Questions

- Can retry detection/labeling be automated (e.g., via a VLM) rather than requiring manual annotation, to make this scalable?
- How does a ReTVL-trained value function perform as an actual RL reward compared to standard progress rewards, not just as a standalone value estimator?

## Significance

Points at an underused data source — the corrective segments inside otherwise-discarded or lightly-used demonstration data — that could improve reward/value models without collecting new data.

## Links

- [Paper](https://arxiv.org/abs/2606.24633)
