---
title: "How to Better Train VLAs: Lessons Learned From the REAL-I Challenge at ICRA 2026"
date: 2026-09-13
topic: VLA
tags: [vla-posttraining, data-curation, staged-adaptation, competition-report, dual-arm-humanoid]
source: https://arxiv.org/abs/2609.13679
venue: "arXiv / ICRA 2026 REAL-I Challenge report"
---

## Summary

A retrospective analysis of the first Real-world Embodied AI Learning (REAL-I) Challenge at ICRA 2026, comparing how competing teams (NUS-CLEAR, RCL-Lab, Deeptouch.ai) adapted pretrained VLAs to a shared dual-arm humanoid platform under a fixed demonstration budget, using different data curation, staged adaptation, checkpoint selection, and action-space design choices.

## Key Contributions

- Cross-team empirical comparison of fine-tuning recipes under identical hardware and demonstration-budget constraints
- Identifies adapting-to-deployment-environment-while-retaining-prior-capability as a key differentiator between teams
- Highlights demonstration-quality-at-appropriate-temporal-scale and suppressing inactive-component errors as practical levers

## Strengths

- Rare controlled, competition-format comparison across independent teams rather than a single group's ablations, reducing confirmation bias in the reported lessons
- Directly actionable guidance for practitioners doing VLA post-training with limited demonstration budgets

## Weaknesses

- Findings are drawn from a small number of teams/systems on one shared platform, limiting statistical generalizability
- As a "lessons learned" report rather than a novel method paper, it offers less mechanistic insight than a dedicated ablation study

## Open Questions

- Would the same lessons (temporal-scale-aware demo quality, checkpoint selection) transfer to single-arm or mobile-manipulation settings?
- Can the winning strategies be distilled into a reusable, automated fine-tuning recipe rather than requiring expert judgment per team?

## Significance

Competition-driven, cross-team retrospectives are uncommon in VLA research and provide grounded, practice-tested guidance on fine-tuning under realistic budget constraints — directly relevant to the vla-posttraining priority theme.

## Links

- [Paper](https://arxiv.org/abs/2609.13679)
