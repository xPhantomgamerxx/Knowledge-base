---
title: "Targeting World Models to Compromise Robot Learning Pipelines"
date: 2026-06-08
topic: WorldModels
tags: [adversarial, data-poisoning, security, robustness, world-model, robot-learning, supply-chain]
source: https://arxiv.org/abs/2606.09499
venue: "arXiv 2606.09499"
---

## Summary

This paper demonstrates that world models used for robot training data generation or environment simulation introduce a new data-poisoning attack surface into the robot learning supply chain. The authors show that an adversary can compromise a world model's generated trajectories to embed malicious behaviours into downstream robot policies, with attacks that are difficult to detect and survive policy training, even without access to the robot policy itself.

## Key Contributions

- Formalisation of world-model data poisoning as a threat vector in robot learning pipelines, distinct from direct dataset poisoning
- Attack methodology: subtle perturbations to world model outputs that steer robot policy learning toward adversarial task behaviours
- Evaluation showing attack success across multiple robot manipulation tasks while remaining undetectable by standard quality filters
- Defence analysis: discussion of detection strategies and limitations, underscoring that existing robustness measures are insufficient

## Significance

As world models become standard infrastructure for scalable robot training data synthesis, this work raises a timely and practical security concern that the robotics community needs to address before wide deployment of world-model-in-the-loop training pipelines.

## Links

- [Paper](https://arxiv.org/abs/2606.09499)
- [HTML](https://arxiv.org/html/2606.09499)
