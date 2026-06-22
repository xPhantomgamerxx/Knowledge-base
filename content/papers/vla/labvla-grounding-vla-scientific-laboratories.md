---
title: "LabVLA: Grounding Vision-Language-Action Models in Scientific Laboratories"
date: 2026-06-11
topic: VLA
tags: [lab-automation, scientific-robotics, protocol-execution, Qwen3-VL, DiT-action]
source: https://arxiv.org/abs/2606.13578
venue: "arXiv 2026"
---

## Summary

LabVLA adapts VLA models to the domain of scientific laboratory automation, where existing policies trained on household or tabletop demonstrations fail due to the unique challenges of transparent liquids, specialized instruments, and rigid protocol workflows. It adapts a Qwen3-VL backbone with a DiT-based action expert to map visual observations, robot state, and written lab protocols into continuous action chunks.

## Key Contributions

- First VLA pipeline targeting scientific laboratory protocols and diverse lab robot embodiments
- Two-stage training: action token pretraining followed by flow-matching policy learning
- Introduces simulated scientific workspaces that capture lab-specific objects and transparent-liquid dynamics
- Demonstrates superior performance on laboratory protocol benchmarks over generic VLA baselines

## Significance

Opens a new application domain for VLAs in life science and chemistry laboratory automation, where precise manipulation of delicate instruments and liquids is essential.

## Links

- [Paper](https://arxiv.org/abs/2606.13578)
- [GitHub](https://github.com/zjunlp/LabVLA)
- [Model Weights](https://huggingface.co/zjunlp/LabVLA-5B-Base)
