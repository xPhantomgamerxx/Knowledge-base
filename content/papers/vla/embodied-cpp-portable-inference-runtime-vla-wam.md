---
title: "Embodied.cpp: A Portable Inference Runtime of Embodied AI Models on Heterogeneous Robots"
date: 2026-07-02
topic: VLA
tags: [deployment, inference, edge, heterogeneous-hardware, c-plus-plus, runtime, efficiency]
source: https://arxiv.org/abs/2607.02501
venue: "arXiv 2607.02501"
---

## Summary

Embodied.cpp is a portable C++ inference runtime for deploying VLA and World-Action Model (WAM) models on heterogeneous edge hardware (CPU/CUDA GPU/NPU) using GGUF weights. It organizes the shared execution path of embodied models into five layers — input adapters, sequence builders, backbone execution, head plugins, and deployment adapters — enabling multi-rate closed-loop control, latency-first batch-1 inference, and extensible embodied I/O across different robots and simulators from one backend.

## Key Contributions

- Unified five-layer architecture that captures the shared execution path across both VLA and WAM models, enabling one backend to deploy both model families
- Latency-first batch-1 inference design specifically for closed-loop embodied deployment, unlike existing runtimes built for request-response serving
- Demonstrated 100% and 91% closed-loop task success rates for VLA deployments; WAM benchmark reduces block memory from 312.2 MiB to 88.1 MiB

## Significance

Solves the fragmented Python-stack deployment problem for production robot embodied AI, making VLA and WAM models practically deployable on constrained edge hardware without model-specific glue code.

## Links

- [Paper](https://arxiv.org/abs/2607.02501)
- [GitHub](https://github.com/SEU-PAISys/Embodied.cpp)
