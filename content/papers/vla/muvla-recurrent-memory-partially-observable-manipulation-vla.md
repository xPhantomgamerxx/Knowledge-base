---
title: "μVLA: On Recurrent Memory for Partially Observable Manipulation in VLA Models"
date: 2026-06-12
topic: VLA
tags: [memory, partial-observability, recurrence, openvla, ablation-study]
source: https://arxiv.org/abs/2606.12497
venue: "arXiv"
---

## Summary

μVLA is a controlled intervention study (not a new foundation model) that asks how much minimal in-backbone recurrence can help VLA policies handle partially observable manipulation, where the current observation alone is not a sufficient statistic for control (e.g., information that is occluded, transient, or established earlier in an episode). It augments the OpenVLA-OFT backbone token sequence with a small bank of learnable memory tokens carried across timesteps, updated through the standard self-attention forward pass, with no auxiliary losses or architectural additions beyond the memory tokens themselves.

## Key Contributions

- A minimal-intervention design: memory is just extra tokens in the existing self-attention sequence, updated via ordinary forward passes and trained end-to-end with truncated backpropagation through time (TBPTT) — no new loss terms, no separate memory module architecture.
- A parameterized family of variants (memory width m, TBPTT length K, and memory update rule — either cross-step gradients or a detached EMA) that lets the authors systematically study which recurrence design choices actually matter, rather than presenting one fixed design.
- Frames the work explicitly as a calibration study of what minimal recurrence buys you, providing a scientific baseline against which more elaborate memory architectures (e.g., MemoryVLA, external memory banks) can be judged.
- Released code (github.com/CognitiveAISystems/muVLA) enabling reproduction of the ablation family.

## Strengths

- The explicit "controlled intervention study" framing is valuable and relatively rare in a field that often ships new architectures without isolating which specific design choice drove the improvement.
- By varying memory width, TBPTT length, and update rule independently, the paper offers a genuinely useful ablation map for anyone deciding how to add memory to an existing VLA backbone.
- Building directly on OpenVLA-OFT keeps the comparison grounded in a widely-used, reproducible base model rather than a bespoke architecture, aiding comparability with other VLA memory work.

## Weaknesses

- Because it is deliberately a minimal, architecture-light approach, it likely cannot capture memory phenomena requiring longer-range or more structured recall (e.g., explicit object permanence over many minutes, or symbolic task-state tracking) that dedicated external-memory architectures target.
- TBPTT-based training of recurrent tokens is known to struggle with long-range credit assignment; the paper's own K parameter sweep presumably surfaces this tradeoff, but any real long-horizon partial observability (well beyond the TBPTT window) may remain unaddressed.
- As a calibration/ablation study, it may not report state-of-the-art absolute success rates against the field's best memory-augmented VLA methods, making it primarily useful as a scientific reference rather than a deployment-ready model.

## Open Questions

- At what task horizon length does the benefit of in-backbone recurrent memory plateau or reverse (due to TBPTT truncation limits)?
- How does the detached-EMA update rule compare to cross-step gradients in terms of training stability versus final task performance across different partial-observability severities?
- Would combining this minimal recurrence with explicit external memory (as in MemoryVLA-style approaches) yield complementary or redundant gains?

## Significance

μVLA is a useful scientific contribution to the VLA memory literature precisely because it resists the urge to propose a flashy new architecture, instead rigorously calibrating what a minimal, principled recurrence mechanism can and cannot do for partially observable manipulation — a reference point that more complex memory-augmented VLA papers should be measured against.

## Links

- [Paper](https://arxiv.org/abs/2606.12497)
- [GitHub](https://github.com/CognitiveAISystems/muVLA)
