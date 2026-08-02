---
title: "Learning while Deploying: Fleet-Scale Reinforcement Learning for Generalist Robot Policies"
date: 2026-05-01
topic: RL-Robotics
tags: [reinforcement-learning, fleet-learning, vla-posttraining]
source: https://arxiv.org/abs/2605.00416
venue: "arXiv"
---

## Summary

Learning while Deploying (LWD), from a team spanning Shanghai Innovation Institute, AGIBOT Finch, and Columbia University, is a fleet-scale offline-to-online reinforcement learning framework for continually post-training a generalist Vision-Language-Action (VLA) policy from data gathered during real deployment. It closes the loop between deployment, shared physical experience across a robot fleet, policy improvement, and redeployment, targeting the long-tail failures and distribution shift that fixed demonstration datasets cannot capture.

## Key Contributions

- A fleet-scale offline-to-online RL loop that continually improves a single generalist VLA policy using autonomous rollouts and human interventions pooled across many deployed robots
- Distributional Implicit Value Learning (DIVL), which learns a distribution over action values and extracts a quantile statistic as the TD bootstrap target, preserving in-distribution value learning while absorbing variability from heterogeneous, sparse-reward fleet replay and reducing overestimation from out-of-distribution maximization
- Q-learning via Adjoint Matching (QAM) for policy extraction, avoiding the unstable multi-step backpropagation through the flow process that direct critic-gradient optimization of flow-based VLA action generators would otherwise require
- Real-world validation on a fleet of 16 dual-arm robots across 8 manipulation tasks, including semantic grocery restocking and long-horizon (3-5 minute) tasks, reaching an average 95% success rate that improves monotonically as fleet experience accumulates

## Strengths

- Tackles a real, systemic problem for generalist VLA policies (offline pretraining alone can't cover deployment-time distribution shift) with an actual fleet-scale deployment, not a simulated proxy for one
- The DIVL + QAM combination is a genuine technical contribution to make off-policy value learning work with flow-matching action heads, an area where naive critic-gradient backprop through the ODE/SDE sampling process is known to be unstable
- Reports the largest gains specifically on long-horizon tasks, which is where fixed-dataset imitation policies are weakest and where the value of continual online correction should show up most clearly
- 16-robot, 8-task, real-hardware scale is unusually large for this literature and lends credibility to the claimed monotonic improvement curve

## Weaknesses

- As with most single-paper fleet-learning claims, it's unclear how much of the reported gain is attributable to the RL algorithm itself versus simply accumulating more (even non-RL) interaction data and interventions — the paper's own ablations isolating DIVL/QAM contribution vs. raw data volume were not surfaced in available summaries
- Fleet-scale RL depends heavily on infrastructure (safe autonomous rollout, human intervention capture, data pooling across robots) that is expensive and organization-specific; reproducibility outside a well-resourced robotics lab/company is a real barrier
- Sparse-reward, heterogeneous fleet data is exactly the regime where value estimation is hardest to validate; the paper's success is reported in aggregate success rate, which can mask failure modes on individual tasks or robots
- No discussion surfaced of how policy regressions or unsafe intervention-triggering behaviors are caught and prevented before they propagate fleet-wide, which is an important safety question in a continually-updating multi-robot system

## Open Questions

- How does LWD handle policy regressions or reward hacking within a continually-updating fleet — is there a rollback or gating mechanism before wider redeployment?
- How does the number of robots in the fleet trade off against wall-clock time to reach a target success rate, i.e. what is the actual sample-efficiency gain from fleet parallelism vs. a single robot collecting the same total data?
- Would DIVL + QAM generalize to other flow/diffusion-based VLA backbones beyond the one used here, or is it tuned to a specific action-generation architecture?

## Significance

LWD is a notable data point for the emerging "deploy-and-improve" paradigm for generalist robot policies, showing that fleet-scale online RL can meaningfully close the gap left by offline pretraining, particularly on long-horizon tasks, and offering a concrete recipe (DIVL, QAM) for stabilizing value-based RL on top of modern flow-matching VLA action heads.

## Links

- [Paper](https://arxiv.org/abs/2605.00416)
- [Project Page](https://finch.agibot.com/research/lwd)
