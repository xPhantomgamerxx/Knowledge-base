---
title: "PlayWorld: Learning Robot World Models from Autonomous Play"
date: 2026-03-09
topic: WorldModels
tags: [autonomous-play, self-supervised, video-world-model, RL-in-world-model, policy-evaluation]
source: https://arxiv.org/abs/2603.09030
venue: "arXiv 2026"
---

## Summary

PlayWorld is a simple, scalable pipeline for training high-fidelity video world simulators entirely from unsupervised robot self-play — the first work to demonstrate autonomous play as an effective training paradigm for robot video world models. A VLM proposes diverse scene-grounded instructions and a generalist policy executes them, capturing contact-rich interactions and failure cases not present in success-biased human demonstrations.

## Key Contributions

- First autonomous play pipeline for training video world models, removing dependency on human demonstrations
- Up to 40% improvement over human-collected data in fine-grained failure prediction and policy evaluation
- Enables RL in the world model, achieving 65% improvement in real-world success rates
- Captures long-tailed physical interactions (collisions, failures) essential for realistic dynamics modeling

## Significance

Autonomous play as a data source for world models is a step toward robots that can continuously improve their internal simulators through self-exploration rather than costly human teleoperation, with demonstrated real-world policy gains.

## Links

- [Paper](https://arxiv.org/abs/2603.09030)
- [Project Page](https://robot-playworld.github.io/)
