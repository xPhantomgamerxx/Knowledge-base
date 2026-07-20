---
title: "Drop-Then-Recovery: How Redundant Are Vision-Language-Action Models?"
date: 2026-06-27
topic: VLA
tags: [vla, model-compression, architecture, redundancy, language-backbone, efficiency]
source: https://arxiv.org/abs/2606.27755
venue: "arXiv 2606.27755"
---

## Summary

This paper introduces DTR (Drop-Then-Recovery), a protocol that systematically removes blocks from a pretrained VLA model and fine-tunes the result to measure which components are genuinely necessary. It reveals a striking asymmetry: language backbones are highly redundant for standard manipulation tasks, while vision and action pathways are far less tolerant to removal.

## Key Contributions

- DTR protocol: drop blocks, fine-tune, measure post-removal recoverability across architectures
- GateProbe: a one-shot virtual-gate sensitivity metric ranking blocks by contribution to downstream action loss
- Strong empirical finding: removing half of LLM blocks in OpenVLA-OFT actually *improves* LIBERO success rate from 95.0% to 98.3%; retaining only two language blocks still recovers baseline performance
- Vision and action pathways are substantially less compressible than the language backbone

## Significance

Provides actionable guidance for VLA compression and architectural design — language backbone capacity inherited from large VLMs far exceeds what robot manipulation actually needs, opening a direct path to leaner and faster VLA models without sacrificing performance.

## Links

- [Paper](https://arxiv.org/abs/2606.27755)
