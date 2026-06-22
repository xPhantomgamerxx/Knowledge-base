---
title: "MemoryWAM: Efficient World Action Modeling with Persistent Memory"
date: 2026-06-18
topic: WorldModels
tags: [persistent-memory, non-markovian, long-horizon, gist-tokens, anchor-frames, efficiency]
source: https://arxiv.org/abs/2606.20562
venue: "arXiv 2026"
---

## Summary

MemoryWAM addresses the fundamental memory-efficiency trade-off in World Action Models (WAMs): methods conditioned only on short windows struggle in non-Markovian environments, while long-history methods face quadratic cost growth. MemoryWAM introduces a hybrid memory design combining recent frames, event-boundary anchor frames, and compact gist tokens that summarize long-range history, with a tailored attention mechanism for efficient retrieval.

## Key Contributions

- Hybrid memory: recent frames (short-term detail) + anchor frames (event boundaries) + gist tokens (compressed long-range summary)
- Tailored attention mechanism enabling efficient joint retrieval of short-term and long-term context
- ~70 percentage-point average success rate improvement over methods relying only on current observation or short-term memory
- Outperforms LingBot-VA, a strong persistent-memory WAM baseline, while reducing latency and GPU memory

## Significance

MemoryWAM demonstrates that persistent, structured memory is essential for deploying world action models on tasks with long-range dependencies, and shows this can be achieved without sacrificing inference efficiency.

## Links

- [Paper](https://arxiv.org/abs/2606.20562)
