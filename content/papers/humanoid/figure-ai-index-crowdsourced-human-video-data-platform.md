---
title: "Figure AI: Index"
date: 2026-08-26
topic: Humanoid
tags: [vla-posttraining, data-collection, human-video, crowdsourcing, industry]
source: https://www.figure.ai/index-app
venue: "blog / press (Figure AI; covered by Forbes, Humanoids Daily)"
---

## Summary

Index is Figure AI's crowdsourced, gig-economy data-collection platform — grown out of the earlier "Project Go-Big" effort — where contributors record themselves performing everyday household and workplace tasks with a provided capture device, get paid per minute, and have that footage fed through a five-stage pipeline into training data for Figure's Helix humanoid policy. Figure reports the platform has ingested 16M+ videos from 108 countries, processes roughly 30 minutes of footage per second, has 44,000+ weekly active users, has paid out $15M to contributors, and is backed by a $1B commitment to data/compute over the next year.

## Key Contributions

- A two-sided crowdsourced data marketplace (self-recording "Creators" plus bookable gig workers) explicitly designed to source first-person human manipulation video at internet scale, rather than relying on lab teleoperation or scripted demonstration collection.
- A five-stage curation pipeline — automated filtering, human fraud review, embedding-based deduplication, task/embedding-cluster rebalancing, and hierarchical annotation — intended to convert noisy crowdsourced footage into usable, diverse training data.
- Published diversity statistics per 1,000 hours collected (373 unique tasks, 1,146 unique objects, 116 unique environments) as a proxy metric for dataset breadth rather than just raw volume.
- A stated intent to directly feed this pipeline into Helix's training loop, positioning human video (not robot teleoperation) as the primary scaling lever for Figure's VLA policy.

## Strengths

- Directly attacks the central bottleneck in humanoid VLA scaling — the cost and throughput ceiling of teleoperated robot data collection — by substituting cheap, distributed human video capture at a scale (16M+ videos, ~30 min/sec ingestion) that no lab teleoperation program can match.
- The explicit fraud-review and deduplication stages acknowledge a real problem with paid crowdsourcing (low-effort or gamed submissions) rather than assuming raw volume equals quality.
- Reporting concrete diversity metrics (tasks/objects/environments per 1,000 hours) is more informative than a raw hour count and allows at least a rough external comparison against other large video-pretraining datasets.

## Weaknesses

- This is a company announcement, not a technical paper — there is no published data on how well footage recorded by paid gig workers with a "provided device" actually transfers to Helix's embodiment (viewpoint, embodiment gap, and action-labeling from unstructured human video are all major unsolved research problems that the announcement does not address).
- Financial and scale figures ($15M paid out, $1B committed, 44,000 weekly active users, 16M+ videos) are self-reported marketing statistics with no independent verification of data quality, retention, or actual usage in a shipped Helix checkpoint.
- Paying contributors per minute of footage creates an incentive structure that can reward padding/repetition over genuinely novel or difficult task coverage; the rebalancing stage is described only at a high level, so it's unclear how well it corrects for this in practice.
- No mention of consent, privacy, or safety review specifics for a platform that has contributors record themselves and presumably their homes/workplaces at scale across 108 countries — a real operational and ethical surface area that the announcement glosses over.
- "Hierarchical annotation" and how human video is actually converted into action-labeled or embodiment-relevant training signal (versus just captioned clips) is not explained in enough technical depth to assess.

## Open Questions

- What fraction of ingested video actually survives the five-stage pipeline and is used in Helix training, and how has that yield changed as volume scaled?
- Has Figure published or will it publish any evidence (benchmark improvement, ablation) that Index-sourced human video measurably improves Helix task success, versus being primarily a scale/PR narrative?
- How is the human-to-humanoid embodiment gap bridged for footage captured by ordinary people with a handheld/wearable device rather than a robot-mounted camera?

## Significance

One of the most aggressive real-data-scaling bets in humanoid robotics to date — if the pipeline's quality-control claims hold, cheap crowdsourced human video could become a dominant source of VLA pretraining/post-training data industry-wide, but as an unpublished company claim it needs independent scrutiny before being treated as a proven method rather than a scale narrative.

## Links

- [Index app](https://www.figure.ai/index-app)
- [Project Go-Big background](https://www.figure.ai/news/project-go-big)
