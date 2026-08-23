---
title: "Imagining Recovery: Inference-Time Counterfactual Realignment for Vision-Language-Action Models"
date: 2026-08-14
topic: VLA
tags: [vla, test-time-adaptation, failure-recovery, inference-time, vla-posttraining]
source: https://arxiv.org/abs/2608.14822
venue: "arXiv"
---

## Summary

This paper introduces CoRe (Counterfactual Realignment), a training-free, inference-time framework that recovers a frozen VLA policy from online disruptions — goal changes, scene shifts, robot-state errors — without needing failure data or retraining. Upon detecting a deviation, CoRe imagines how the policy would have continued from a recent viable state using synthesized observations, then minimally realigns the robot/scene to rejoin that imagined trajectory.

## Key Contributions

- A training-free recovery mechanism that requires no failure-case dataset and no fine-tuning of the base policy, in contrast to most VLA recovery methods which retrain on curated failure/recovery pairs.
- A counterfactual framing: instead of directly correcting the current bad state, the method reconstructs what the policy "would have done" from a still-viable earlier state and steers execution back toward that imagined continuation.
- Targets a class of disruptions (goal changes, scene shifts, state errors) broader than the contact-slip or grasp-failure recovery scope common in prior work.

## Strengths

- Training-free deployment is a genuine practical advantage — it can be layered onto any existing frozen VLA without a separate fine-tuning pass or curated failure corpus.
- Addressing goal/scene-level disruptions, not just low-level execution slips, covers a failure mode (environment or instruction changing mid-task) that most recovery papers in this vault do not directly target.

## Weaknesses

- The method depends on synthesizing plausible "imagined" observations for a counterfactual trajectory; the fidelity of this synthesis under significant scene change is the crux of the approach and is not detailed in available coverage.
- Detecting *when* a deviation warrants counterfactual realignment (versus normal task variation) is itself a hard problem — false positives could trigger unnecessary and disruptive realignment.

## Open Questions

- How does CoRe distinguish a genuine disruption from ordinary stochastic task variation, and what is the false-positive rate in practice?
- Does the "minimal realignment" step have failure modes where scene edits themselves introduce new physical inconsistencies the base policy then mishandles?

## Significance

Adds a training-free entry to the fast-growing body of test-time recovery and adaptation work for VLA policies (alongside FAR, HAVE, and Retrieve-then-Steer already logged here), notable specifically for avoiding any dependency on curated failure data.

## Links

- [Paper](https://arxiv.org/abs/2608.14822)
