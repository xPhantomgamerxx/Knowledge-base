---
title: "From Pretraining to Proficiency: Real-World Subtask RL for Long-Horizon Manipulation with Minimal Human Intervention"
date: 2026-09-21
topic: RL-Robotics
tags: [rl-finetuning, subtask-rl, long-horizon, human-in-the-loop, vla-posttraining]
source: https://arxiv.org/abs/2609.21788
venue: "arXiv"
---

## Summary

PARTS (Policy Adaptation with RL on Targeted Subtasks) concentrates RL fine-tuning effort on the specific subtask "bottlenecks" where a pretrained foundation policy fails within an otherwise-working long-horizon task, rather than fine-tuning the whole trajectory uniformly. A frozen pretrained policy supplies nominal actions throughout, while agent-generated selectors and success verifiers activate residual corrections and provide local outcome rewards only where needed. On bimanual YAM and single-arm Franka setups, complete-task success rises from 32% to 61% and from 50% to 95% respectively, using only tens of minutes of real RL per task.

## Key Contributions

- Automatically localizes which subtask(s) in a long-horizon chain are the actual failure bottleneck, rather than treating the whole trajectory as a uniform RL target
- Keeps the base policy frozen and intervenes only locally via residual corrections, minimizing risk of degrading already-working subtasks
- Demonstrates large success-rate gains (32%→61%, 50%→95%) with only tens of minutes of real-robot RL — a notably tight compute/time budget for real-world fine-tuning

## Strengths

- Targeting the bottleneck subtask directly, instead of spreading RL signal across an entire long trajectory, is an efficient use of scarce real-world interaction time and plausibly reduces credit-assignment difficulty
- The magnitude of improvement (nearly doubling or reaching near-ceiling success) on a tens-of-minutes real-RL budget is a strong practical result if it generalizes beyond the two tested platforms
- Keeping the frozen base policy as the default action source is a sensible safety-conscious design that limits how much damage a poorly-trained residual correction can do

## Weaknesses

- Relies on automatic bottleneck localization (selectors/verifiers) working correctly — if the subtask localization is wrong, the limited RL budget gets spent in the wrong place, and this failure mode isn't characterized
- Two platforms (bimanual YAM, single-arm Franka) and presumably a handful of tasks is a narrow base from which to claim general applicability to "long-horizon manipulation" broadly
- "Minimal human intervention" is somewhat underspecified in the available summary — the actual human effort involved in setting up selectors/verifiers per task isn't quantified

## Open Questions

- How does PARTS handle tasks with multiple simultaneous bottlenecks, or bottlenecks that shift location as the base policy improves?
- Could the selector/verifier components themselves be learned end-to-end rather than hand-specified per task, to reduce setup overhead?

## Significance

A practically important contribution to the growing cluster of sample-efficient real-world RL fine-tuning methods for long-horizon tasks, where naive whole-trajectory RL is often prohibitively expensive in real-robot time.

## Links

- [Paper](https://arxiv.org/abs/2609.21788)
- [Project page](https://destiny000621.github.io/PARTS/)
