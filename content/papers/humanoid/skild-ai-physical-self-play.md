---
title: "Skild AI: Physical Self-Play"
date: 2026-09-23
topic: Humanoid
tags: [humanoid, self-play, rl-finetuning, post-training, vla-posttraining]
source: https://www.skild.ai/blogs/physical-self-play
venue: "blog"
---

## Summary

Skild AI describes a post-training technique for their S1 foundation model in which a policy competes against checkpoints of its recent past self in simulated soccer, accumulating over 140 simulated years of self-play before transferring to a physical humanoid that then plays against humans and other robots. Before self-play, S1 was first trained on individual soccer skills using human references and skill-specific rewards; the self-play stage then combined and adapted those capabilities through competition, with behaviors like dribbling past a defender, shielding the ball, and tackling emerging without hand-crafted rewards for those specific behaviors — they arose because they helped the model score.

## Key Contributions

- Demonstrates self-play (policy vs. recent self-checkpoints) as a viable post-training stage for a general physical-AI foundation model, not just a narrow sports-specific RL system
- Shows emergent tactical behaviors (dribbling, shielding, tackling) arising from a single scoring-oriented objective rather than hand-engineered per-behavior rewards
- Explicit two-stage recipe: human-reference skill pretraining first, then self-play competition to combine/refine those skills — a sensible decomposition of "basic competence" from "competitive refinement"
- Real physical-humanoid transfer and competition, not just simulated self-play results

## Strengths

- Self-play's historical success in producing superhuman, creative strategies (games, board games) is a compelling precedent, and this is a credible attempt to bring that paradigm to general-purpose physical-AI post-training beyond hand-authored reward shaping
- The two-stage design (skill pretraining, then self-play) is a reasonable answer to the usual self-play bootstrapping problem — starting self-play from scratch without any skill prior would likely be far less sample-efficient
- Explicitly stated intent to extend the approach to "several day-to-day robotics tasks beyond sports" signals this is framed as a general post-training technique, not a one-off sports demo

## Weaknesses

- As a company blog post rather than a peer-reviewed paper, technical details (exact RL algorithm, how self-play opponent selection/curriculum is managed, sim-to-real transfer specifics) are largely unavailable for independent scrutiny
- 140 simulated years is an enormous compute budget; the cost-effectiveness and accessibility of this approach for smaller labs or less-resourced teams is an open practical question
- Soccer is a task with a clean, dense-ish proxy objective (scoring); it's unclear how directly the self-play recipe generalizes to "day-to-day robotics tasks" that lack an equally natural competitive or scoring framing

## Open Questions

- What does self-play look like for tasks without a natural adversarial or competitive structure (most household/industrial manipulation tasks)?
- How much of the 140-simulated-year budget is actually necessary versus front-loaded compute that could be reduced with better curriculum design or sample efficiency techniques?

## Significance

A high-profile industry signal that self-play — long a staple of game-playing AI — is being seriously explored as a general post-training paradigm for physical foundation models, potentially opening a new axis of post-training beyond imitation and single-agent RL fine-tuning.

## Links

- [Blog post](https://www.skild.ai/blogs/physical-self-play)
