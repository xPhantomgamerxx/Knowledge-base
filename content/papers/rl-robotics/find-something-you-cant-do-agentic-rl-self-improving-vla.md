---
title: "Find Something You Can't Do: Agentic Real-World Reinforcement Learning for Self-Improving VLA Models"
date: 2026-09-25
topic: RL-Robotics
tags: [rl-finetuning, agentic-rl, self-improvement, vla-posttraining]
source: https://arxiv.org/abs/2609.32069
venue: "arXiv"
---

## Summary

FIND is an agentic real-world RL framework that closes the loop between scene understanding, weakness-aware practice, self-evaluation, and policy improvement without resetting to a predefined scene after each rollout. Instead, it reframes autonomous practice as scene-conditioned, performance-aware task selection: the leftover scene state after a rollout determines what to practice next. Across eight real manipulation tasks, human-assessed success improves from 55% to 71.9%, with a representative run completing 456 autonomous episodes in six hours, needing only 30 human scene-recovery interventions and no human-provided reward labels during online learning.

## Key Contributions

- Replaces the standard "reset-and-retry" autonomous practice loop with scene-conditioned task selection, letting the robot exploit whatever state the environment happens to be in rather than wasting effort resetting
- Removes the need for human-provided reward labels during online learning, relying on self-evaluation
- Reports concrete autonomy metrics (456 episodes in 6 hours, only 30 interventions) that make the practical cost of this approach legible

## Strengths

- The scene-conditioned task-selection reframing is a genuinely different idea from most self-improvement loops, and plausibly more sample/time-efficient since it doesn't throw away "free" practice opportunities from leftover scene state
- Reporting intervention count (30 scene-recovery interventions) alongside the headline success-rate gain gives a realistic picture of how "autonomous" this really is, rather than overselling full autonomy
- 55% → 71.9% on eight real tasks is a meaningful, human-verified improvement, not just a simulated or self-reported metric

## Weaknesses

- Self-evaluation (no human reward labels) risks the policy optimizing against its own flawed judgment of success — reward hacking against a self-assessment model is a real concern not deeply addressed
- 30 scene-recovery interventions across 456 episodes is low but nonzero; the framework's reliance on occasional human intervention means it isn't yet a fully unattended solution
- Eight tasks, while real, is still a bounded testbed; how task diversity or difficulty affects the viability of scene-conditioned selection isn't explored

## Open Questions

- How robust is the self-evaluation mechanism to subtle failure modes that look superficially successful (e.g., object placed near but not at the target)?
- Does the scene-conditioned approach degrade gracefully or catastrophically as the number of concurrent tasks/objects in the workspace grows?

## Significance

A compelling real-world demonstration that autonomous practice can be made meaningfully more efficient by exploiting rather than resetting environment state — directly relevant to making real-world RL fine-tuning of VLAs practical at scale without constant human supervision.

## Links

- [Paper](https://arxiv.org/abs/2609.32069)
