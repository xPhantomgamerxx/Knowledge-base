---
title: "World Action Agent: Harnessing VLMs for Robot Manipulation via World Action Rehearsal"
date: 2026-09-24
topic: WorldModels
tags: [world-models, vlm-agent, test-time-adaptation, vla-posttraining]
source: https://arxiv.org/abs/2609.29964
venue: "arXiv"
---

## Summary

World Action Agent (WAA) is a multi-agent harness in which a VLM pilots a robot by turning each candidate action into an editable proposal, "rehearsing" it via an Imagination Agent that previews and revises the proposal against planning feedback before execution, closing the loop between observation, rehearsal, and low-level execution. On LIBERO-Pro it reaches 75.6% average success using skills evolved only from LIBERO-90, outperforming end-to-end VLAs and code-as-policy agents; fine-tuning a smaller model (Qwen3.5-9B) on harness-generated traces raises OOD success from 1.7% to 43.3%.

## Key Contributions

- Introduces "action rehearsal" — treating each action as an editable, previewable proposal rather than a committed output — as a mechanism for VLM-driven manipulation
- Automatically selects contact views from scene geometry, addressing the perennial problem of VLMs reasoning over poorly-framed visuals
- Shows harness-generated interaction traces are themselves a valuable training signal, dramatically improving a smaller model's OOD generalization when fine-tuned on them (1.7% → 43.3%)

## Strengths

- The rehearsal/preview mechanism is a plausible way to reduce costly physical trial-and-error by catching obviously bad actions before execution, rather than only reacting after failure
- Using the harness as a data-generation engine for a smaller downstream model is a compelling practical pattern: an expensive VLM-agent system distilled into a cheap deployable policy
- 75.6% on LIBERO-Pro using only LIBERO-90-derived skills (i.e., no extra task-specific data) suggests genuine compositional generalization rather than benchmark-specific tuning

## Weaknesses

- Rehearsal-based planning likely adds significant per-action latency (multiple VLM calls per decision), which the paper doesn't quantify — a real concern for anything beyond slow, quasi-static manipulation
- 43.3% OOD success after distillation, while a large relative improvement, is still a modest absolute number — the harness's "intelligence" doesn't fully transfer to the distilled model
- Evaluated only on LIBERO-family benchmarks; no real-robot validation reported

## Open Questions

- What is the real wall-clock latency of the rehearsal loop, and how does it scale with task complexity or number of candidate actions considered?
- How much of the harness's benefit comes from the VLM's general reasoning versus the specific rehearsal/imagination mechanism — would a simpler re-prompting strategy capture similar gains?

## Significance

A strong example of using world-model-style "imagination" not to replace the policy but to scaffold a VLM agent's decision-making, and crucially, as a scalable data engine for bootstrapping smaller deployable models — directly relevant to the VLA post-training data pipeline.

## Links

- [Paper](https://arxiv.org/abs/2609.29964)
- [GitHub](https://github.com/ZYH-Lightyear/world-action-agent)
