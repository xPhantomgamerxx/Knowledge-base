---
title: "Retrieve, Don't Retrain: Extending Vision Language Action Models to New Tasks at Test Time"
date: 2026-06-18
topic: VLA
tags: [vla-posttraining, retrieval-augmented-policy, cross-embodiment, test-time-adaptation, human-video, few-shot-tasks]
source: https://arxiv.org/abs/2606.15631
venue: "arXiv"
---

## Summary

This paper replaces per-task fine-tuning of VLA policies with retrieval: a retrieval-augmented policy is trained once on paired demonstrations from a target embodiment (the "query" side) and a cheaper-to-collect embodiment such as human-hand video (the "pool" side), and is then frozen. New tasks are added purely by indexing new pool-side demonstrations into the retrieval database — the frozen policy conditions on retrieved trajectories at every control step, so no further training is needed to acquire new tasks, only to acquire a genuinely new embodiment.

## Key Contributions

- A retrieval-augmented policy architecture that conditions on retrieved cross-embodiment demonstrations at each control step, decoupling "learning to act" (trained once) from "learning a new task" (handled by retrieval-pool indexing).
- Use of human-hand video as the cheap pool-side data source, reported to be roughly 18x faster to collect than equivalent target-embodiment teleoperated demonstrations, substantially lowering the cost of adding new tasks.
- Demonstration that retrieval augmentation benefits multiple policy backbones, with an especially pronounced effect on Cosmos Policy, a video-generation-based world-action model (WAM).
- Evaluation on PushT (showing the retrieved motion prior generalizes to unseen goal angles) and RoboTwin 2.0 (outperforming cross-embodiment baselines on unseen tasks), plus a real-robot demonstration.

## Strengths

- Reframing "new task acquisition" as a data-indexing problem rather than a training problem is a genuinely different point in the design space from the dominant fine-tuning/in-context-learning approaches, and directly targets the practical cost of teleoperated demonstration collection.
- Using human-hand video as the cheap pool side is a pragmatic choice that leverages abundant, low-cost data sources instead of requiring teleoperated robot data for every new task.
- Testing across multiple backbones (including a video-generation-based world-action model) suggests the retrieval mechanism is not narrowly tailored to one architecture.

## Weaknesses

- The policy is frozen with respect to new tasks but the paper concedes fine-tuning is still required to handle a genuinely new embodiment — the approach only eliminates per-task adaptation cost, not per-embodiment adaptation cost, which limits how far "don't retrain" really extends.
- Retrieval quality is presumably bottlenecked by how well pool-side (e.g., human-hand) demonstrations align with the target embodiment's action space and viewpoint; the abstract-level description does not make clear how robust the approach is when the retrieval pool is sparse, noisy, or covers only loosely related tasks.
- Evaluation centers on PushT and RoboTwin 2.0 (largely simulation-oriented benchmarks) with only a single real-robot demonstration mentioned, so it's unclear how well retrieval-based task acquisition holds up across a broad range of real-world manipulation tasks and clutter/lighting conditions.

## Open Questions

- How does retrieval-pool size and task diversity affect zero-shot performance on genuinely novel tasks — is there a point where the retrieval index becomes too large or too noisy to be effective at inference time?
- What is the latency/compute cost of retrieval at every control step in a real-time control loop, and how does this scale with retrieval pool size?
- Could the retrieval mechanism itself be extended to also handle new embodiments without fine-tuning, e.g., via embodiment-conditioned retrieval keys?

## Significance

By showing that new-task acquisition can be handled through retrieval-pool indexing rather than fine-tuning, and that cheap human-hand video can substitute for costly teleoperated data on the pool side, this work offers a scalable alternative to the per-task fine-tuning paradigm that dominates current VLA deployment workflows.

## Links

- [Paper](https://arxiv.org/abs/2606.15631)
- [HTML](https://arxiv.org/html/2606.15631v1)
