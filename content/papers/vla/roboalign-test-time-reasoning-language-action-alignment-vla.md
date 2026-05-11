---
title: "RoboAlign: Learning Test-Time Reasoning for Language-Action Alignment in Vision-Language-Action Models"
date: 2026-03-22
topic: VLA
tags: [RL-alignment, test-time-reasoning, language-action, LIBERO, CALVIN, reinforcement-learning]
source: https://arxiv.org/abs/2603.21341
venue: "arXiv 2603.21341"
---

## Summary

RoboAlign is a two-stage MLLM training framework that bridges the modality gap between language and low-level robot actions in VLA models using reinforcement learning. Stage 1 integrates embodied reasoning with FAST-tokenized action generation via supervised fine-tuning; Stage 2 applies RL to refine token-level action accuracy and language-action alignment using fewer than 1% of training samples.

## Key Contributions

- Two-stage pipeline: SFT for embodied reasoning integration, then RL for action accuracy alignment
- Zero-shot natural language reasoning to sample action tokens, refined via RL without large demonstration datasets
- Achieves 17.5%, 18.9%, and 106.6% performance improvements over SFT baselines on LIBERO, CALVIN, and real-world environments respectively

## Significance

Shows that RL-based alignment post-SFT can yield dramatic real-world gains with minimal extra data, positioning test-time reasoning alignment as a critical but underexplored axis for VLA improvement.

## Links

- [Paper](https://arxiv.org/abs/2603.21341)
- [HTML](https://arxiv.org/html/2603.21341)
