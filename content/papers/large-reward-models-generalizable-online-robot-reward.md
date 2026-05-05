---
title: "Large Reward Models: Generalizable Online Robot Reward Generation with Vision-Language Models"
date: 2026-03-17
topic: RL-Robotics
tags: [reward-model, VLM, online-RL, imitation-learning, robot-manipulation, sample-efficient]
source: https://arxiv.org/abs/2603.16065
venue: "arXiv"
---

## Summary

Large Reward Models (LRM) adapts foundation VLMs into frame-level, online reward generators for closed-loop RL policy refinement. Rather than evaluating trajectories post-hoc, LRM generates a multifaceted reward signal — comprising process, completion, and temporal contrastive rewards — from current visual observations. Starting from an imitation-learning base policy, LRM-guided RL achieves significant success rate improvements within just 30 RL iterations.

## Key Contributions

- VLM-based online reward generator producing process, completion, and temporal-contrastive reward signals
- Multi-source training dataset: real robot trajectories, human-object interactions, and simulated environments
- Frame-level reward computation from current visual observations, not full-trajectory post-hoc evaluation
- Closed-loop correction of sub-optimal IL policy behaviors with remarkable sample efficiency (30 RL iterations)

## Significance

LRM eliminates the need for manual reward engineering in robot RL while achieving practical sample efficiency, making RL-based robot policy refinement viable in real-world deployment pipelines. Generalizable VLM-based reward models may become a standard component of future robot learning stacks.

## Links

- [arXiv](https://arxiv.org/abs/2603.16065)
- [Project Page](https://yanru-wu.github.io/Large-Reward-Models/)
