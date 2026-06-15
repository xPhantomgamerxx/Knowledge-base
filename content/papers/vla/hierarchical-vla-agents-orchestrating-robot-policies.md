---
title: "What Matters in Orchestrating Robot Policies: A Systematic Study of Hierarchical VLA Agents"
date: 2026-06-09
topic: VLA
tags: [hierarchical-VLA, hi-VLA, options-framework, task-decomposition, VLM-planner, Google-DeepMind, systematic-study]
source: https://arxiv.org/abs/2606.10267
venue: "arXiv 2606.10267"
---

## Summary

This Google DeepMind paper provides the first systematic study of hierarchical VLA (Hi-VLA) systems, where a high-level VLM planner decomposes tasks into language sub-goals executed by a low-level VLA controller. By unifying representative Hi-VLA architectures under an options-style control framework and benchmarking core design choices across short-horizon, long-horizon, and reasoning-intensive tasks, it distils practical principles for building effective Hi-VLA systems.

## Key Contributions

- Unified options-style control framework that formally captures the design space of Hi-VLA planners, controllers, switching mechanisms, and observation/memory representations
- Comprehensive benchmark across diverse task categories revealing how planner choice, interface mechanisms, and memory representations jointly determine Hi-VLA performance
- Practical design principles: quantitative evidence of which architectural choices matter most (e.g., sub-goal representation granularity, replanning frequency, context window size)
- Analysis of when hierarchical decomposition helps versus when it hurts compared to flat VLA baselines

## Significance

The first principled empirical guide for building hierarchical VLA systems, directly actionable for practitioners; particularly relevant as long-horizon and reasoning-intensive tasks increasingly require modular planning beyond what flat VLAs can achieve.

## Links

- [Paper](https://arxiv.org/abs/2606.10267)
- [HTML](https://arxiv.org/html/2606.10267v1)
