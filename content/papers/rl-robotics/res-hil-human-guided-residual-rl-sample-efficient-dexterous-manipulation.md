---
title: "Res-HIL: Human-Guided Residual Reinforcement Learning for Sample-Efficient Dexterous Manipulation"
date: 2026-09-24
topic: RL-Robotics
tags: [rl-finetuning, human-in-the-loop, residual-rl, dexterous-manipulation, vla-posttraining]
source: https://arxiv.org/abs/2609.30023
venue: "arXiv"
---

## Summary

Res-HIL is a human-in-the-loop residual RL framework that keeps a pretrained imitation policy frozen and learns a residual correction policy on top, where human-generated interventions both directly supervise the residual policy and shape an otherwise sparse task reward via intervention occurrence. With only 20 initial demonstrations, it outperforms state-of-the-art full-policy HIL-RL and residual-RL-without-human-guidance after just ten minutes of online training, on five real-world contact-rich tasks (precise insertion, long-horizon cable manipulation).

## Key Contributions

- Dual use of human interventions: as direct supervision for the residual policy's corrective actions, and as an implicit reward signal (intervention occurrence) for an otherwise sparse task reward
- Demonstrates competitive performance against both full-policy HIL-RL and non-human-guided residual RL baselines, isolating the specific value of human guidance in the residual setting
- Strong sample efficiency: only 20 demonstrations plus ten minutes of online training to outperform baselines and 5x-larger imitation-only datasets

## Strengths

- The dual-use-of-interventions design is an efficient way to extract more signal per costly human intervention, rather than treating interventions as pure supervision or pure reward but not both
- Outperforming imitation policies trained with 5x more demonstrations, using only 20 demos plus residual RL, is a compelling sample-efficiency result if it holds across task types beyond the five tested
- Keeping the base policy frozen while learning only a residual correction is a safety-conscious and interpretable design, consistent with other 2026 residual-RL work (e.g., VLaRL, HAF-Steer)

## Weaknesses

- Five tasks, all contact-rich manipulation, leaves open how well the dual-use intervention signal generalizes to tasks with different failure characteristics (e.g., tasks where failures are not well localized to a correctable residual)
- Reliance on live human interventions during training, even if brief (ten minutes), is still a scarce and non-scalable resource compared to fully autonomous self-improvement approaches (e.g., FIND)
- No analysis of how intervention quality/consistency (noisy or inconsistent human correction, as studied in GAINS) affects Res-HIL's performance

## Open Questions

- How does Res-HIL perform when human interventions are noisy or inconsistent, rather than the presumably clean interventions used in evaluation?
- Could the dual-use intervention signal be combined with autonomous self-practice (à la FIND) to reduce the human-time budget further while retaining the sample efficiency?

## Significance

A strong addition to the human-in-the-loop RL literature specifically for dexterous, contact-rich manipulation, demonstrating that modest human guidance budgets can meaningfully outperform both larger imitation datasets and fully autonomous residual RL.

## Links

- [Paper](https://arxiv.org/abs/2609.30023)
