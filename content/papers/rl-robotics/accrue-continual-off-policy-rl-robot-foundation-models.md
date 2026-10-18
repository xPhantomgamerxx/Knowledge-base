---
title: "ACCRUE: Continual Off-Policy Reinforcement Learning for Robot Foundation Models"
date: 2026-10-13
topic: RL-Robotics
tags: [reinforcement-learning, continual-learning, off-policy, foundation-model, real-robot-rl]
source: https://arxiv.org/abs/2610.18596
venue: "arXiv (NVIDIA / KAIST)"
---

## Summary

ACCRUE is a continual off-policy RL framework for robot foundation models that carries lightweight actor and critic networks across tasks, letting each new RL stage reuse knowledge from earlier stages instead of relearning from scratch — reported to cut real-robot RL training time by 31–68.5% on contact-rich assembly tasks, in both simulation and on real hardware.

## Key Contributions

- An inherited-critic mechanism: the critic from a prior task adapts only on current-task transitions and is used to guide current-task actor learning, rather than training a fresh critic per task.
- An actor-preservation mechanism that distills the actor toward cached targets on a small set of retained episodes, aiming to prevent catastrophic forgetting of earlier tasks while the current task is being learned.
- Real-hardware validation of the training-time reduction, not just simulation.

## Strengths

- A 31–68.5% reduction in real-robot training time is a substantial, practically meaningful number if it holds up — real-robot RL time is one of the biggest bottlenecks to iterating on robot foundation models.
- Targeting contact-rich assembly specifically is a sensible choice, since this is a task class where RL fine-tuning is known to be sample-inefficient from scratch.
- Combining critic inheritance with actor-preservation-via-distillation is a reasonably principled way to balance plasticity (learning the new task) against stability (not forgetting old ones), which is the core tension in continual RL.

## Weaknesses

- The reported range (31–68.5%) is wide, and per the available secondary coverage, the paper doesn't break down which specific tasks or conditions land at which end of that range — without that detail it's hard to know how representative the headline number is.
- Based only on secondary summaries rather than the primary arXiv listing at time of writing, so the base-policy architecture, parameter counts, and full experimental protocol aren't independently confirmed here.

## Open Questions

- How many sequential tasks can ACCRUE's actor/critic inheritance scheme handle before the retained-episode distillation budget becomes a bottleneck, or before accumulated drift degrades inherited performance?
- How does ACCRUE's continual off-policy approach compare against purely offline continual-learning methods (e.g., generative replay for WAMs, logged elsewhere this week) that avoid needing any new real-robot rollouts at all?

## Significance

A concrete, hardware-validated reduction in real-robot RL training time for contact-rich tasks is directly useful to anyone scaling RL fine-tuning of robot foundation models across many sequential tasks — exactly the kind of practical efficiency gain the field needs as RL post-training becomes more standard.

## Links

- [Paper](https://arxiv.org/abs/2610.18596)
