---
title: "Learning From History: Test-Time Verification and Adaptation for Robotics (HAVE)"
date: 2026-07-06
topic: VLA
tags: [vla, test-time-adaptation, vla-posttraining]
source: https://publications.ri.cmu.edu/storage/publications/2026/07/main_20260706112439.pdf
venue: "CMU Robotics Institute"
---

## Summary

This CMU Robotics Institute paper (associated with researcher Yilin Wu) introduces HAVE, a test-time verification and adaptation architecture that ranks candidate robot actions by conditioning on the robot's own history of past attempts and their outcomes, rather than treating each action proposal independently. It matters because it offers a way for a policy to exploit its own recent trial-and-error experience within a single deployment episode — using PointNet++ encoders for 3D geometric understanding of proposed and historical actions combined with self-attention over the history — to select better actions or verify success without further training.

## Key Contributions

- Proposes an explicit-attention verifier architecture: proposed actions and historical actions are each encoded with PointNet++ (for 3D geometric structure), with historical outcomes encoded similarly, then related via an attention mechanism where the current proposal (query) attends to similar past actions (keys) and reads off their recorded outcomes
- Frames test-time adaptation as history-conditioned action ranking/verification rather than gradient-based weight updates, avoiding the instability risks of online fine-tuning at test time
- Demonstrates faster task completion via history-based adaptation, e.g., completing an uneven-object manipulation scenario in 3 steps versus 5 for a conditional baseline
- Shows that the explicit attention design is more robust than a monolithic/vanilla transformer baseline when the estimated history of outcomes is noisy (e.g., when success/failure signals come from imperfect observation-based estimation rather than ground truth)
- Evaluates on articulated-object and uneven-object manipulation scenarios, including verifier analysis and comparisons between conditional and unconditional action generators

## Strengths

- Avoids the risks of test-time weight updates (catastrophic forgetting, instability) by instead using history as conditioning context for verification/ranking — a lighter-weight and arguably safer form of test-time adaptation
- Explicitly tests robustness to noisy outcome estimation, which is realistic since in real deployments success/failure signals are often estimated (e.g., via vision) rather than given by an oracle
- The 3D-aware (PointNet++) encoding of actions and history is well-suited to manipulation tasks where geometric relationships (contact points, object pose) are central to whether a past attempt's lesson transfers to a new proposal
- Focuses on articulated and uneven-object manipulation, which are harder, less rigid-body-friendly settings than typical pick-and-place benchmarks

## Weaknesses

- Available details on the overall quantitative benchmark suite (task diversity, number of trials, baselines beyond "conditional generator") are limited from public summaries, making it hard to fully judge generality
- History-conditioned ranking presumably requires accumulating a non-trivial number of past attempts within an episode or across episodes before it helps — cold-start behavior (first attempt, no history) is not clearly addressed
- As with most test-time verification approaches, there's a dependency on having a reasonably informative outcome/success signal at all — in genuinely ambiguous failure cases, the verifier may struggle to disambiguate causes
- Being a CMU tech-report/publication rather than a widely-indexed arXiv paper, it's harder to cross-check details against community discussion or follow-up citations

## Open Questions

- How many historical attempts are needed before HAVE's ranking provides a reliable benefit over an unconditional baseline?
- Does the approach generalize to long-horizon, multi-stage tasks where "history" spans different sub-goals rather than repeated attempts at the same action?
- How does HAVE compare against gradient-based test-time training approaches (e.g., TTT-VLA style latent prompt optimization) on the same benchmarks — is history-conditioned verification strictly safer, or also less powerful?

## Significance

HAVE contributes to a growing family of test-time adaptation techniques for robot policies that avoid the pitfalls of online weight updates by instead leveraging in-context history, relevant to the broader push toward robots that can self-correct during deployment without requiring retraining or human intervention.

## Links

- [Paper (PDF)](https://publications.ri.cmu.edu/storage/publications/2026/07/main_20260706112439.pdf)
