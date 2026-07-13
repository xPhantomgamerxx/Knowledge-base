---
title: "Embodied-R1.5: Evolving Physical Intelligence via Embodied Foundation Models"
date: 2026-06-11
topic: VLA
tags: [embodied-foundation-model, rl, planner-grounder-corrector, qwen3, multi-task, self-correction]
source: https://arxiv.org/abs/2606.11324
venue: "arXiv 2606.11324"
---

## Summary

Embodied-R1.5 is a unified Embodied Foundation Model built on Qwen3-VL-8B that integrates embodied cognition, task planning, self-correction, and pointing within a single architecture. Three automated data construction pipelines build a 15B-token training corpus. A Planner-Grounder-Corrector (PGC) closed-loop framework enables the model to autonomously execute and self-correct over long-horizon tasks, and with light action-data fine-tuning it becomes Embodied-R1.5-VLA for direct continuous action output.

## Key Contributions

- Planner-Grounder-Corrector (PGC) framework unifying high-level reasoning, spatial grounding, and self-correction in one model without separate modules
- Multi-task balanced RL recipe addressing heterogeneous task conflict across 24 embodied VLM benchmarks; achieves SOTA on 16 of 24, surpassing Gemini-Robotics-ER-1.5 and GPT-5.4
- Embodied-R1.5-VLA fine-tune outperforms leading VLA models including π₀.₅ across 4 popular manipulation benchmark suites

## Significance

Demonstrates that a single relatively small (8B) foundation model, trained with multi-task RL and a comprehensive data pipeline, can exceed much larger proprietary embodied models — and can be directly extended to low-level action control.

## Links

- [Paper](https://arxiv.org/abs/2606.11324)
- [GitHub](https://github.com/pickxiguapi/Embodied-R1.5)
- [Project page](https://embodied-r.github.io/)
