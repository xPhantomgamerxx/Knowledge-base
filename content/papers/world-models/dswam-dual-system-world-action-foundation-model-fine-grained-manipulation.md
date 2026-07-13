---
title: "DSWAM: A Dual-System World Action Foundation Model for Fine-Grained Robot Manipulation"
date: 2026-07-06
topic: WorldModels
tags: [dual-system, world-action-model, task-decomposition, planning, manipulation, system-1-system-2]
source: https://arxiv.org/abs/2607.04927
venue: "arXiv 2607.04927"
---

## Summary

DSWAM addresses a key limitation of existing World Action Models (WAMs): they excel at physical execution but lack explicit language-level planning for decomposing coarse instructions. DSWAM maintains a System 1 WAM executor as the default control path and optionally activates a System 2 VLM subtask planner only when task decomposition is needed — running in WAM-only mode for atomic instructions and invoking System 2 for coarse multi-step commands.

## Key Contributions

- Dual-system architecture: System 1 (WAM executor) runs by default for all tasks; System 2 (VLM planner) is activated selectively only when coarse instruction decomposition is beneficial, preserving efficiency for simple tasks
- System 2 predicts an ordered sequence of executable subtasks from short-term visual history and the global task prompt, enabling fine-grained decomposition of household-level goals
- Foundation model design: trains a single unified WAM with both execution and optional planning paths rather than two separate models

## Significance

Shows that the VLA advantage in instruction decomposition and the WAM advantage in physically grounded execution are not mutually exclusive — a dual-system design can capture both, outperforming pure WAMs and VLAs on complex multi-step manipulation benchmarks.

## Links

- [Paper](https://arxiv.org/abs/2607.04927)
