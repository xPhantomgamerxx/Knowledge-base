---
title: "Intrinsic Robot Rewarding: Reusing VLA Representations for Autonomous Evaluation and Policy Improvement"
date: 2026-09-15
topic: RL-Robotics
tags: [vla-posttraining, reward-modeling, self-improvement, autonomous-evaluation]
source: https://arxiv.org/abs/2609.17115
venue: "arXiv"
---

## Summary

Proposes computing reward "intrinsically" inside a VLA's existing perception pipeline by comparing new task outcomes against a reference bank of successful demonstration endpoints in the frozen visual encoder's own feature space — no separate learned reward model or extra perception backbone is needed.

## Key Contributions

- Reuses the policy's own frozen visual encoder as the feature space for scoring outcomes, rather than training a dedicated reward/evaluator model
- Defines task-specific references from successful demonstration endpoints, plus a scoring operation that adds a reference bank to the existing VLA pipeline
- Develops the reward formulation and supporting evidence on representation quality, physical learning, efficiency, and transfer for autonomous policy improvement

## Strengths

- Architecturally minimal — no extra model to train or maintain — which is attractive for closed-loop autonomous improvement at deployment
- Directly ties reward quality to the same representations the policy already uses for control, potentially aligning reward and policy failure modes rather than introducing a mismatched external judge

## Weaknesses

- A frozen encoder's feature-space proximity to reference endpoints is a fairly coarse notion of "success" and is plausibly gameable (reward hacking toward visual similarity rather than true task completion)
- Endpoint/reference-based scoring may struggle with tasks that have multiple valid outcome configurations or highly variable success states
- As a very recent submission, independent validation/replication is not yet available

## Open Questions

- How robust is the reward to visually similar-but-functionally-wrong outcomes (the classic reward-hacking failure mode for representation-similarity rewards)?
- How does this compare against learned VLM reward models on the same tasks in terms of both reward quality and downstream policy improvement?

## Significance

A "free" reward signal reused from the policy's own representations, if reliable, would meaningfully lower the barrier to closed-loop autonomous self-improvement for deployed VLA fleets, which is one of the field's stated end goals.

## Links

- [Paper](https://arxiv.org/abs/2609.17115)
