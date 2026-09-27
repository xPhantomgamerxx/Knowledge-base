---
title: "In-Context Robot Learning with VLM Agents"
date: 2026-09-27
topic: VLA
tags: [vla, in-context-learning, vlm-agents, zero-shot]
source: https://arxiv.org/abs/2609.19138
venue: "arXiv"
---

## Summary

This paper introduces GPT-Policy, an agentic framework that uses a general-purpose vision-language model to perform in-context robot learning at deployment time — adapting to a new task from demonstrations and interaction feedback without gradient updates or persistent parameter changes. It comprises a context compiler that preserves task-relevant visual transitions, a VLM that proposes robot-tool actions, and a constrained controller that verifies and executes each proposed action.

## Key Contributions

- Frames in-context robot adaptation explicitly as an agentic loop (compile context → propose action → verify/execute → report outcome) rather than a single conditioning-and-generate step, giving the system a feedback channel absent from most in-context imitation baselines.
- Shows human video demonstrations (without robot action labels) still improve task completion when passed through the context compiler, suggesting the VLM can extract usable structure from action-free demonstrations.
- Evaluates with matched cross-model comparisons and controlled context ablations rather than a single end-to-end number, isolating which context components actually help.

## Strengths

- Avoiding gradient updates at deployment sidesteps catastrophic forgetting and safety concerns that come with online weight updates on hardware.
- The finding that action-unlabeled human video still helps is practically important: it lowers the bar for what counts as usable in-context data.
- The constrained controller for verifying/executing proposed actions is a sensible safety layer that many "VLM directly outputs actions" pipelines lack.

## Weaknesses

- Relying on a commercial frontier VLM ("GPT-6 Astra") for the core reasoning loop raises questions about latency, cost, and reproducibility for labs without access to equivalent proprietary models.
- In-context approaches without weight updates are known to plateau below fine-tuned specialist policies on tasks requiring precise, high-frequency control; the paper's own framing (task success and efficiency metrics) suggests this trade-off is present but doesn't fully quantify it against RL/fine-tuning baselines.
- "Contact-sensitive tasks" benefiting from aligned action references implies the pure zero-shot, action-free setting is meaningfully weaker exactly where robotic manipulation is hardest.

## Open Questions

- How does GPT-Policy's success rate scale with the number and diversity of in-context demonstrations, and where is the practical ceiling on context length/latency trade-offs?
- Is the constrained controller sufficient to catch systematically wrong but locally plausible action proposals, or only obviously invalid ones?
- Would this approach transfer to embodiments dissimilar from those seen at VLM pretraining time, given the reliance on a general-purpose (non-robot-specialized) backbone?

## Significance

It is a timely demonstration that frontier general-purpose VLMs, when wrapped in the right agentic scaffolding, can perform meaningful in-context robot adaptation without any weight updates — directly relevant to the cross-cutting priority of test-time adaptation and in-context imitation learning for VLAs.

## Links

- [Paper](https://arxiv.org/abs/2609.19138)
