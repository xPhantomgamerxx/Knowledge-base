---
title: "Playful Agentic Robot Learning"
date: 2026-06-17
topic: RL-Robotics
tags: [agentic-RL, autonomous-play, code-as-policy, skill-library, self-directed-exploration]
source: https://arxiv.org/abs/2606.19419
venue: "arXiv 2026"
---

## Summary

Playful Agentic Robot Learning introduces RATs (Robotics Agent Teams), a framework where an embodied coding agent uses self-directed play as a continual skill-learning stage before downstream tasks arrive. During play, RATs proposes novel yet learnable exploratory tasks, executes Code-as-Policy programs, verifies intermediate progress, diagnoses failures with dense step-level feedback, and distills successful executions into a persistent code skill library reused at test time.

## Key Contributions

- Self-directed play paradigm for proactive skill acquisition before any task instruction is given
- RATs multi-agent architecture: task proposer, executor, verifier, and failure-diagnoser agents working in concert
- Persistent code skill library distilled from play experiences, enabling few-shot reuse at test time
- 20.6 and 17.0 percentage-point gains over no-play CaP-Agent0 baseline on LIBERO-PRO and MolmoSpaces
- Code and implementation released at GitHub

## Significance

Demonstrates that robot agents can autonomously build reusable skill libraries through play before ever receiving a task, moving robotic learning toward a more human-like developmental paradigm where skills are acquired through exploration rather than instruction.

## Links

- [Paper](https://arxiv.org/abs/2606.19419)
- [Project Page](https://playful-rats.github.io/)
- [GitHub](https://github.com/Playful-RATs/rats)
