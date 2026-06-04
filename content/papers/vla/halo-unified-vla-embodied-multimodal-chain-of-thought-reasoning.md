---
title: "HALO: A Unified Vision-Language-Action Model for Embodied Multimodal Chain-of-Thought Reasoning"
date: 2026-02-27
topic: VLA
tags: [chain-of-thought, multimodal-reasoning, visual-subgoal, mixture-of-transformers, ICML-2026, long-horizon]
source: https://arxiv.org/abs/2602.21157
venue: "ICML 2026"
---

## Summary

HALO introduces Embodied Multimodal Chain-of-Thought (EM-CoT) reasoning into VLA models via a three-stage pipeline: textual task reasoning, visual subgoal prediction for fine-grained guidance, and EM-CoT-augmented action prediction. It addresses the failure of existing VLAs in long-horizon and out-of-distribution scenarios caused by their lack of explicit reasoning and world-state anticipation.

## Key Contributions

- Unified EM-CoT framework that sequentially performs text reasoning → visual subgoal generation → action prediction in one model
- Mixture-of-Transformers (MoT) architecture with specialized experts for semantic reasoning, visual foresight, and action prediction, connected via shared self-attention
- Experiments show significant improvements on long-horizon tasks compared to VLAs lacking explicit reasoning mechanisms
- Decoupled expert design retains scalability while enabling rich cross-modal interaction

## Significance

HALO provides a principled, human-like reasoning framework for VLAs that unifies textual and visual chain-of-thought, filling a key gap in the field's ability to handle complex sequential manipulation tasks.

## Links

- [Paper](https://arxiv.org/abs/2602.21157)
- [ICML 2026 Poster](https://icml.cc/virtual/2026/poster/61922)
