---
title: "π0.7: a Steerable Generalist Robotic Foundation Model with Emergent Capabilities"
date: 2026-04-16
topic: VLA
tags: [compositional-generalization, steerable, multi-task, cross-embodiment, flow-matching, physical-intelligence]
source: https://arxiv.org/abs/2604.15483
venue: "arXiv 2026"
---

## Summary

π0.7 is a 5B-parameter VLA from Physical Intelligence that achieves compositional generalization — the ability to combine skills learned in different contexts to solve tasks never seen during training. By enriching prompts with language commands, subgoal images, episode metadata, and strategy descriptions, the model learns to steer behavior at inference time without fine-tuning, enabling zero-shot cross-embodiment transfer including laundry folding on a UR5e bimanual system for which it had zero training data.

## Key Contributions

- Rich multi-modal context conditioning (language + subgoal images + strategy metadata) as the core steering mechanism
- Emergent compositional generalization: recombines motor skills like linguistic tokens to solve novel task combinations
- Zero-shot cross-embodiment control demonstrated on a UR5e bimanual system for dexterous tasks (laundry folding, air fryer cooking) matching expert teleoperator performance
- 5B-parameter architecture built on a 4B VLM backbone with a MEM-style video history encoder and 860M-parameter action expert

## Significance

The first robotic foundation model to demonstrate convincing compositional generalization at scale, representing a meaningful step toward a general-purpose robot brain that can be pointed at unfamiliar tasks and coached via language without additional training data.

## Links

- [Paper](https://arxiv.org/abs/2604.15483)
- [PDF](https://www.pi.website/download/pi07.pdf)
- [Blog Post](https://www.pi.website/blog/pi07)
