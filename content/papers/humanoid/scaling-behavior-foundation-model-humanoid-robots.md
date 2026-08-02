---
title: "Scaling Behavior Foundation Model for Humanoid Robots"
date: 2026-07-16
topic: Humanoid
tags: [humanoid, foundation-models, whole-body-control]
source: https://arxiv.org/abs/2607.15163
venue: "arXiv"
---

## Summary

ScaleBFM, from Shanghai AI Lab and collaborators, is a systematic scaling study for humanoid Behavior Foundation Models (BFMs) that examines three levers together — the learning paradigm (global-frame motion tracking rather than local-frame), training data (a 102-million-frame, 50 FPS human motion corpus aggregated from multiple open datasets and retargeted to the target humanoid), and model architecture (a new "Humanoid Transformer"). It follows the authors' earlier "Behavior Foundation Model" work and reports large reductions in whole-body motion-tracking error, most notably an 82% drop in Mean Per-Keypoint Position Error in global-frame mode over prior methods.

## Key Contributions

- A global-frame motion-tracking formulation that reframes diverse humanoid control problems as reproducing integrated whole-body behaviors in absolute (world) coordinates rather than relative/local frames
- A 102-million-frame human motion dataset built by aggregating and retargeting multiple existing open-source motion-capture corpora to the target humanoid's morphology, reaching foundation-model-scale training data without new large-scale mocap collection
- The "Humanoid Transformer," an architecture designed to let structured behavioral representations emerge naturally from scale
- A joint scaling analysis treating learning paradigm, data, and architecture as separable axes, reporting MPKPE reductions of over 10% in local-frame mode and 82% in global-frame mode versus prior humanoid controllers

## Strengths

- Explicitly decomposing "what to scale" into paradigm, data, and architecture is methodologically cleaner than presenting one entangled change, and helps isolate which factor is actually driving improvement
- Global-frame tracking directly addresses a known weakness of local/relative-frame imitation approaches — drift accumulation and poor awareness of absolute position — which matters for tasks requiring coordinated, multi-step whole-body behavior
- An 82% MPKPE reduction in global mode is a large, specific, quantified result, and it builds cumulatively on the authors' prior BFM work rather than being a one-off announcement
- Aggregating and retargeting data from multiple existing open motion datasets is a pragmatic path to foundation-model-scale training data without requiring new large-scale motion capture campaigns

## Weaknesses

- Available sources do not clarify how much of the reported system has been validated on real hardware versus evaluated purely in simulation against the MPKPE tracking metric
- Motion-tracking accuracy is a proxy for imitation fidelity, not for downstream task success; a model with lower MPKPE is not automatically better at accomplishing goal-directed loco-manipulation tasks
- Architectural specifics of the "Humanoid Transformer" (parameter count, tokenization scheme, exact attention structure) are not detailed in the sources available, making it hard to assess its novelty relative to other transformer-based motion models in the field
- Retargeting human motion capture onto humanoid morphology is a known lossy process (foot sliding, joint-limit violations, contact mismatches); scaling data volume alone does not inherently resolve morphology-transfer artifacts unless explicitly addressed by the pipeline

## Open Questions

- How does the scaled BFM perform on real humanoid hardware and on downstream task success rates, rather than just motion-tracking error, compared to task-specific RL or imitation policies?
- Which of the three scaling axes (paradigm, data, architecture) contributes most to the reported gains, and do they interact or scale independently?
- Does the resulting "versatile library of movements" support zero-shot composition into novel long-horizon behaviors, or does it mainly improve fidelity on motions similar to the training distribution?

## Significance

ScaleBFM is a rare systematic scaling study for humanoid behavior foundation models that treats learning paradigm, data scale, and architecture as separable levers, and its large reported gains from reframing control in the global frame suggest that how a control problem is formulated can matter as much as how much data or model capacity is applied — a lesson with relevance beyond humanoids to embodied foundation models generally.

## Links

- [Paper](https://arxiv.org/abs/2607.15163)
- [Project Page](https://scalebfm.github.io/)
- [GitHub](https://github.com/zengweishuai/ScaleBFM)
