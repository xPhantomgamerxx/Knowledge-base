---
title: "VLA-Pro: Cross-Task Procedural Memory Transfer for Vision-Language-Action Models"
date: 2026-05-29
topic: VLA
tags: [VLA, procedural-memory, LoRA, cross-task-transfer, continual-learning]
source: https://arxiv.org/abs/2605.29562
venue: "arXiv 2605.29562"
---

## Summary

VLA-Pro is a plug-and-play framework that adapts task-relevant manipulation patterns at inference time using a procedural memory bank. The current procedural state (summarizing ongoing execution stage) queries the bank, which stores task-specific LoRA adapters as parameterized procedural experience; retrieved adapters are fused into the base VLA to reuse relevant patterns while avoiding interference from unrelated task behaviors.

## Key Contributions

- Procedural state extraction module for querying a task-specific LoRA adapter memory bank
- Each bank entry stores a task-specific LoRA adapter encoding a distinct manipulation pattern
- Runtime adapter fusion enables cross-task knowledge transfer without full retraining
- Plug-and-play design compatible with existing VLA backbones

## Significance

VLA-Pro frames cross-task generalization as a memory retrieval problem, achieving dynamic adaptation at inference time—an approach that scales naturally as the skill library grows without modifying the base model.

## Links

- [Paper](https://arxiv.org/abs/2605.29562)
