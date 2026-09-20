---
title: "Helix 2.5: Zero-Shot 30-Home Generalization"
date: 2026-09-17
topic: Humanoid
tags: [figure-ai, helix, vla, human-video-pretraining, zero-shot-generalization, company-blog]
source: https://www.figure.ai/news/helix-2-5-zero-shot-30-home-generalization
venue: "blog"
---

## Summary

Figure announced Helix 2.5, which it calls its most advanced neural network yet, demonstrating Figure 03 robots performing household chores (tidying, towel folding, bed making) across 30 previously unseen Bay Area homes with zero per-home data collection, fine-tuning, or adaptation.

## Key Contributions

- "Index" human-experience pretraining pipeline reportedly generating ~35 minutes of new human video/experience data per second, used to pretrain locomotion and whole-body generalization instead of relying solely on robot teleoperation data
- Reports zero-shot whole-task success rising from 9% to 56% across 420 real-home trials (237 trials with no partial credit) after Index pretraining
- Claims the resulting policy needs roughly half the task-specific data of the prior Helix 02 policy to reach comparable performance

## Strengths

- Real-world evaluation spans 30 distinct home environments rather than a single lab/demo house, which is a meaningfully larger and more heterogeneous test bed than most humanoid demos
- Explicit ablation-style framing (with vs. without Index pretraining, 9% vs 56%) is more quantitative than typical company demo posts
- Represents a genuine architectural/data-strategy shift away from teleop-bottlenecked data collection toward internet/human-video-scale pretraining

## Weaknesses

- No peer review, no released paper, no independent replication; all numbers are self-reported by Figure with no disclosed statistical methodology, trial protocol, or task difficulty breakdown
- "30 homes" selection criteria are undisclosed (recruited/vetted homes may not represent worst-case clutter, lighting, or object diversity)
- No failure-mode analysis, safety incident reporting, or discussion of what the ~44% of trials that didn't reach whole-task success looked like

## Open Questions

- How much of the gain is attributable to Index-style pretraining versus other concurrent changes (model scale, action head, hardware revisions)?
- Does the zero-shot generalization hold outside the Bay Area / outside similarly-resourced households (different furniture styles, languages, clutter levels)?
- What is the robot's behavior on failure — does it recover gracefully or fail unsafely, and how often does it require human intervention mid-task?

## Significance

If the reported numbers hold up under scrutiny, this is one of the clearest public claims yet that human-video-scale pretraining (rather than teleoperated robot data) can drive large jumps in humanoid zero-shot home generalization, directly bearing on the industry-wide debate about the most data-efficient path to general-purpose humanoid deployment.

## Links

- [Blog](https://www.figure.ai/news/helix-2-5-zero-shot-30-home-generalization)
