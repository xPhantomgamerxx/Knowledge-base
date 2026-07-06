---
title: "RHO: Your Coding Agent is Secretly a Roboticist"
date: 2026-06-16
topic: RL-Robotics
tags: [RL-Robotics, code-as-policy, neuro-symbolic, skill-discovery, reward-learning, code-generation]
source: https://arxiv.org/abs/2606.16458
venue: "arXiv 2606.16458"
---

## Summary

Robotics Harness Optimization (RHO) is a paradigm where tool-enabled coding agents, at training time, propose and search for interpretable neurosymbolic multi-file policy repositories that compose robotics primitives—rather than relying on multi-turn code-generation loops at test time. RHO uses reflective feedback from environment reward and execution (not teleoperation demonstrations), achieving 45.0% on LIBERO-PRO (2.5× vs. strongest multi-turn agentic system) and setting a new SOTA of 70.0% on Robosuite with single-turn execution.

## Key Contributions

- RHO: trains coding agents to search for reusable neurosymbolic policy repositories at training time
- Reflective reward-based feedback replaces demonstration-based supervision
- Interpretable multi-file policy repositories composed of reusable robotics primitives
- 45.0% on LIBERO-PRO (2.5× over multi-turn agentic baselines)
- New SOTA 70.0% on Robosuite with single-turn execution

## Significance

RHO reframes robot policy synthesis as a program synthesis problem solved by RL—showing that coding agents with environment feedback can outperform imitation-based methods on manipulation benchmarks.

## Links

- [Paper](https://arxiv.org/abs/2606.16458)
